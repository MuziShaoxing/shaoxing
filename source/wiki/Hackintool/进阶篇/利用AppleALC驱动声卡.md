
---
layout: wiki
wiki: Hackintool
title: 进阶篇-利用AppleALC驱动声卡
order: 608
---
> 版权©️声明 : 本文章出自[套陆](https://blog.tlhub.cn/Driver-audio-for-hackintosh.html）
------------
# 前言

> 在vit9696推出AppleALC后，经过越来越多人仿冒声卡得到的数据的提交整理，AppleALC的数据越来越集中，也使声卡驱动变得越来越简单。
>
> 本文提供使用AppleALC驱动声卡的思路以及常见错误和驱动后的问题进行修复。

## 前期准备

- 需要下载Xcode

  > 在AppleStore下载

- 下载AppleALC

  > 通过终端执行下面的命令，会下载到你的用户根目录



```
git clone https://github.com/vit9696/AppleALC
```

- 下载

  ```
  Lilu
  ```

  > 在下面的网址下载DEBUG和RELEASE



```
https://github.com/vit9696/Lilu/releases
```

- 提取

  ```
  Codec
  ```

  > 这一步需要用到Linux环境，首先下载Ubuntu镜像，我个人提供一个



```
链接:http://pan.baidu.com/s/1i47I0jN  密码:de4v
```

> 当然也可以去官网下载，下载好镜像之后，将U盘格式化为Fat32，然后将镜像解压到U盘，重启以U盘启动，选择试用进入Ubuntu系统界面，打开终端输入



```
cat /proc/asound/card0/codec#0 > ~/Desktop/Codec.txt
```

> 执行完后会将Codec.txt提取到桌面，将其保存到U盘

PS: 一般来说提取的Codec会有10k左右大小，如果大小不够，很有可能提取错误，可以尝试以下命令



```
cat /proc/asound/card0/codec#1 > ~/Desktop/Codec.txt
```

> 或者



```
cat /proc/asound/card0/codec#2 > ~/Desktop/Codec.txt
```

> 或者



```
cat /proc/asound/card1/codec#0 > ~/Desktop/Codec.txt
```

## Codec.txt的数据整理

- 记录Address和Vendor Id值

> Codec.txt开头部分



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0rlxkhmkj31qc1f6awh.jpg)



- 提取节点信息

> 搜索Pin Default记录Node和节点描述，以我的为例



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0rp1h1zqj31qc1f6tu9.jpg)



PS: N/A节点无效无需整理

- 记录HP Out at Ext Left节点的tag和enable值

> PS: Unsolicited Response的设定是为了解决耳机和外放切换的问题。
> 需设定 HP Out at Ext 所在的节点，并且节点信息中有Unsolicited: tag=xx, enabled=1 这一行。
> 设定命令为Address+NodeID+708+<设定值>
>
> 设定值是8位的一个二进制数，记作a7 a6 a5 a4 a3 a2 a1 a0，推算出此二进制数之后，四四拆分转换为2位的十进制数加1即为此设定值
>
> a7表示enabled。
> a6=0，没具体应用，不用管。
> a5~a0，存放tag。

- 记录Mic at Ext节点的Pin-ctls值

> PS: Pin Control Widget的设定是为了解决耳机杂音的。
>
> 需要设定的是 Mic at Ext 所在的节点，设定的值可以从codec dump中读取。
>
> 设定命令是 Address+NodeID+707+Pin-ctls值。

> 整理完后，会得到如下所示的数据集合



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0ruzqsv0j31qc1f6h0k.jpg)



PS: 常见的节点设备描述如下：

> Mic at Ext–线路输入(耳麦)
>
> Mic at In–内建输入
>
> HP Out–耳机扬声器
>
> Speaker–内建扬声器(外放)

至此，Codec 数据的整理到此结束

## AppleALC中数据的筛选

> 依次打开下载的AppleALC源码里面/AppleALC/Resources/PinConfigs.kext/Contents下的Info.plist
>
> 搜索之前记录的CodecID



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0rr0c3j7j31i21fc1bi.jpg)



> 记录搜索到的所有的ID中的configdata，如下整理



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0rtddnoij31qc1f6tn4.jpg)



> 每一行的每一串的第一个字符代表Address值

> 每一行的第三串倒数第二个字符代表这个节点的设备描述，具体对应关系如下



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0rsd7nz6j30u00zagt5.jpg)



> 根据上图设备对应关系和Address值排除掉无效的ID数据

## 开工

- 将下载的Debug的Lilu.kext放进 AppleALC 源码根目录；
- 删除/AppleALC/Resources中多余文件夹，只留下你的声卡型号文件夹、Pinconfigs.kext以及四个plist文件，以cx20751这个声卡为例剩下如下文件



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0rwbp9r0j31js11i12t.jpg)



- 然后打开计算器，显示为编程器



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0rwzv78dj30sc0wmdm0.jpg)



- 打开你整理的Codec，找到Vendor Id，拷贝后面的字符串，在计算器选中十六进制，粘贴这个字符串



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0rxl8nrzj30sc0wmgqq.jpg)



- 然后选中十进制，就换转换成十进制形式



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0rxs4ee3j30sc0wmdl1.jpg)



- 拷贝这个十进制数，打开/AppleALC/Resources/CX20751_2/Info.plist(此处的CX20751_2需要换成你的声卡型号)，把codecid换成刚才拷贝的十进制数



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0rzb85g2j31i21fcam3.jpg)



- 保存退出，右键PinConfigs.kext显示包内容，打开里面的Info.plist，搜索刚才拷贝的十进制数，记下LayoutID数据，有几个记几个，都记下来，然后将IOKitPersonalities->HDA Hardware Config Resource->HDAConfigDefault中的其他型号删除，(为避免出错，这里的删除可以不操作，删除只是为了精简做出来的AppleALC)，保存退出。
- 然后双击打开 AppleALC 中的工程文件：



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0s19qdobj32cg1fau0r.jpg)



- 按图示操作



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0s1lqb2zj32gy1fa1kx.jpg)



- 点击右面的Distribute Content



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0s2jqwz6j320w18q7h5.jpg)



- next



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0s2qqvltj320w18qnaw.jpg)





![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0s3cxnnhj320w18qaoa.jpg)



- Export As填上桌面，点export就生成AppleALC在桌面上了，一层一层打开它，将其中的AppleALC.kext放到clover驱动目录，注意之前下载的Release的Lilu也要放到clover驱动目录，最后不要忘了注入LayoutID：



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0s69hvhfj31rg1fi4fa.jpg)



- 如果重启后你的声卡不能驱动，或者已驱动但是没有输入或输出，这时很有可能是该LayoutID对应的configdata数据有错误，这时就挨个尝试刚才记录的所有ID。

至此， AppleALC 驱动声卡部分结束。

## 关于解决耳机与内建输入的切换

> 如果驱动工作完成后，声卡可以工作，但不能自动切换，请接着往下看

- 打开终端，输入



```
git clone https://github.com/goodwin/ALCPlugFix 
```

- 回车就将ALCPlugFix下载到了你的用户目录，打开此目录中的ALCPlugFix中的main.m下拉到最下方，注意这一部分：



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0s84o8vij31qc1f6twi.jpg)



- 下载[CodecCommander](https://github.com/RehabMan/EAPD-Codec-Commander.git)





```
git clone https://github.com/athlonreg/ALCPlugFix.git
git clone https://github.com/RehabMan/EAPD-Codec-Commander.git
cp ALCPlugFix/alc_fix/hda-verb /usr/local/bin/
cd EAPD-Codec-Commander
./widget_dump.sh 
```

- 回车



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0swd71qcj31p818kank.jpg)



- 找到nid = 0x19和nid = 0x1a，这里我的19为 line in，1a为mic in，记录下最后两位，我的是04和24就这么改

PS: 这里需要设定的节点数据分别是line in和mic in，其他节点无效，思想就是捕获系统在不插耳机时由于其输入输出正常的这两个节点的输出值，然后就可以知道插耳机正常应该输出的值，进而利用AppleALC守护进程动态守护。如果出现插耳机正常，不插无效的情况，请按照这个思路反过来操作，思想都是一样的。其中图上的高亮处最上面一部分是默认情况，中间是耳机移除，最下面是耳机插入，请结合自身使用情况合理设定



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0syo8oezj31qc1f6qqy.jpg)



- 保存退出，双击按照AppleALC的编译方法编译这个
- 然后将生成的ALCPlugFix替换alc_fix中的ALCPlugFix，终端cd到alc_fix目录，执行



```
./install.sh
```

- 耳机就可以自动切换了，三节点的朋友运气好的话杂音应该也解决了，这时插入耳机在执行



```
./widget_dump.sh 
```

- 就可以发现之前的19和1a后面的数据反过来了(我这里是修复好的，就不再演示了。。。)

> 其实这里的数据就是侦测耳机插拔状态，向系统发送相关指令来做到切换正常
>
> 需要设定的就是两个节点Mic at Ext(有时是Line In)和Mic at In
>
> Mic at Ext(有时是Line In)表示线路输入，即耳麦，多为0x19节点
>
> Mic at In为内建输入

- 如果不行重启一次应该就好了。

至此，解决耳机与内建输入的切换部分结束。

## 关于唤醒无声

> 可以先尝试下面两个驱动
>
> [CodecCommander](https://github.com/RehabMan/EAPD-Codec-Commander)
> [EAPDFix](http://pan.baidu.com/s/1nuTUVS9) 提取密码:w4yr

PS: 关于CodecCommander，可以[点击这里](https://github.com/RehabMan/EAPD-Codec-Commander/blob/master/README.md)参考RehabMan的说明

> 另外四叶草助手中也提供了相关选项(ResetHDA和dartweak)，但是本人没有亲自尝试，大家可以自行尝试这些组合：



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0stj21kcj3220180dvi.jpg)





![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0st47xc9j32201801a0.jpg)



本人对唤醒无声研究不多，至此，解决耳机与内建输入的切换部分结束，欢迎补充。

## 关于万能声卡

> 很多人不喜欢万能声卡，说万能有杂音(但是有一些人的AppleALC也可能有杂音)，甚至说用万能声卡是不完美的表现，其实我认为不然，万能是一种很好的渠道，有不少人用万能声卡，他们的切换、输入甚至HDMI都能很好的输出，而且杂音也是可以减小的。
>
> 这里我给出官方的项目地址，有兴趣的可以试一下
>
> https://sourceforge.net/projects/voodoohda/

PS: 需要注意的是有人用的是VoodooHDA.pkg安装的，这种情况需要将AppleHDADisabler.kext放到Clover的驱动目录来禁用AppleHDA，否则很有可能会造成KP五果，所以我建议直接用kext，让Clover注入器注入即可。

## 关于完整仿冒

### 前言

> 声卡型号众多，虽然AppleALC让数据更集中了，但还是有些声卡不在目前的AppleALC支持的列表里面，对于这种情况来说，我们只能完整制作仿冒声卡。
>
> 接下来以我的CX20751为例简述仿冒声卡制作过程。

### 完整制作仿冒声卡思路

- 整理Codec，提取所有有效Node值
- 将整理出的所有Node的Pin Default值进行转换得出需要的值
- 根据某些规律或者规则得出ConfigData
- PathMap的获取和整理

### 知识普及

> 每一个Node的ConfigData值都是由四个八位的字符串组成，这四个串的最后两位分别是一个八位的设定值的1 2、3 4、5 6、7 8位，这四个八位的字符串的设定规则分别是是Address+Node+71C+1 2位设定值、Address+Node+71D+3 4位设定值、Address+Node+71E+5 6位设定值、Address+Node+71F+7 8位设定值。
>
> 这里需要注意，有两个不同的八位被提及，其中一个八位(这八位每一位都有特定的含义，也是仿冒成功最关键的地方，在后面我称之为设定值)是被均分四份从而放到ConfigData的各个节点所对应的四个串的七八位
>
> 而这个八位的设定值每一位的含义如下：

- 第一位：代表节点设定值(Address)，一般不需要改变；
- 第二位：同组装置的优先顺序，一般为 0~3，不可出现字母；
- 第三位：插口颜色，笔记本忽略，不作处理；
- 第四位：插孔侦测，0为开启(外设基本为0)，1为关闭(内建基本为1)；
- 第五位：装置类型，笔记本忽略；
- 第六位：连接类型，圆口为1，内接为0，基本可以忽略；
- 第七位：代表是否有插孔及插孔位置0=外接，9=内建，耳机扬声器和耳麦均为外接；
- 第八位：代表插孔所在位置，0=内建，1=外接；

### 开始

#### 整理Codec，提取所有有效Node值

> 与上面利用AppleALC的思路不同，这里我们需要提取的数据有设备描述、Node值和Pin Default值。具体提取方法上文已有说明，这里不再赘述，下面是我的CX20751提取的数据：



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0t2suhufj31qc1f64ef.jpg)



#### 将整理出的所有Node的Pin Default值进行转换修正得出需要的设定值

- 对于Pin Default值，我们的处理方法为八位四分、二二逆置，例如0x16节点，首先得出40 10 21 03，同理得出：



```
0x16: 40 10 21 03
0x17: 10 01 17 90
0x19: 30 10 A1 03
0x1a: 20 01 A7 95
```

> 根据八位设定值的规则描述，对上面得出的设定值进行修正。
>
> 拿0x16为例，这是一个耳机扬声器节点。
>
> 第1、2、3位没什么好说的保持不变；
> 第4位插孔侦测，耳机设备属于外接设备，所以应当是0，这里是0不用动；
> 第5位装置类型笔记本忽略；
> 第6位连接类型，插口为圆口，所以是1，这里是1，保持不变；
> 第7位代表是否有插孔，耳机是外接设备，所以是0，这里是0，保持不变；
> 第8位插孔所在位置，耳机是外接设备，所以是1；
>
> 其他Node节点也是如此设定；
>
> 修正后的数据如下：



```
0x16: 40 10 21 01
0x17: 10 01 17 90
0x19: 30 10 81 01
0x1a: 20 01 A0 90
```

#### 根据规律或者规则得出ConfigData

> 根据上面得出的设定值，我可以得出以下ConfigData值：



```
01671C40 01671D10 01671E21 01671F01
01771C10 01771D01 01771E17 01771F90
01971C30 01971D10 01971E81 01971F01
01a71C20 01a71D01 01a71EA0 01a71F90
```

PS: 搜索一下codec里面有没有EAPD这个字符串，有的话就在ConfigData的最后面加上一串01470C02这组数字。

#### PathMap的获取和整理

> 在声卡仿冒的过程中这一步是最麻烦的。有几个需要注意的地方。
>
> 对于声音节点来说，节点路径的推断遵循一个规律：
>
> 输入是从后往前推断节点，输出是从前往后推。

- 首先利用codecgraph得到路径图，该操作需要安装graphviz，这里我推荐利用终端npm install graphviz安装即可，然后执行下面的命令下载codecgraph



```
git clone https://github.com/athlonreg/codecgraph.git 
```

- 这样就下载到了你的用户根目录，将你的Codec.txt拷贝到下载的codecgraph目录下，然后



```
cd codecgraph
./codecgraph Codec.txt
```

- 就在codecgraph目录下生成了你的声卡路径图，格式为svg，用safari即可打开，当然也可以转换为其他格式，例如我的



![img](https://cdn.jsdelivr.net/gh/athlonreg/BlogImages/Images/006dLY5Ily1fy0t3vra4yj31u60f2n07.jpg)



- 可以看到0x16节点只连接了0x10，HP Out为输出，从前往后推，转换为十进制得到0x22 -> 0x16;
- 0x17节点只连接了0x11，Speaker为输出，从前往后推，转换为十进制得到0x23 -> 0x17;
- 0x19节点只连接了0x14，Mic at Int为输入，从后往前推，转换为十进制得到0x20 -> 0x25;
- 0x1a节点只连接了0x13，Mic at Ext为输入，从后往前推，转换为十进制得到0x19 -> 0x26;

> 整理得到路径如下：

| 设备名称    | 有效节点 | 路径                  |
| :---------- | :------- | :-------------------- |
| HP Out      | 0x16     | 0x22->0x16            |
| Speaker Out | 0x17     | 0x23->0x17            |
| Mic In      | 0x1a     | 0x26<-0x19 0x26<-0x20 |
| Line In     | 0x19     | 0x25<-0x20 0x26<-0x19 |

PS: 我的声卡比较奇葩，对于多数声卡来说，输入一般为0x8 -> 0x35 -> 0x18，输出一般为0x33 -> 0x13 -> 0x3

## AppleHDA 修改

## Credit

[vit9696](https://github.com/vit9696)
[goodwin](https://github.com/goodwin/ALCPlugFix)
[RehabMan](https://github.com/RehabMan)
[Dolnor](https://github.com/Dolnor/EAPD-Codec-Commander)
[daliansky](https://github.com/daliansky)
[VoodooHDA](https://sourceforge.net/projects/voodoohda/)
