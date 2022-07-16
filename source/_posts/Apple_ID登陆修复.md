---
title: Apple_ID登陆修复
abbrlink: ca810459
cover: >-
  https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/shaoxing/20210910/22:31-111.png
dark: true
tags:
  - 修复
date: 2021-04-21 20:45:00
categories:
  - 黑苹果教程
---
## 故障描述
黑苹果后登陆apple id提示：
- 无法验证您的设备或电脑,请联系技术支持寻求帮助
- 发生未知错误
- 登陆iCloud英文报错
- 等各种错误情况,这是因为你的网卡没有{% emp 内建 %}.

这里简单说下网卡内建:

## 确认故障
1. 首先用Hackintool查一下网卡内建信息
- [Hackintool 中文版 (黑苹果必备工具箱)](https://github.com/headkaze/Hackintool/releases）

![WDuD3o](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/WDuD3o.png)
2. 查看网卡设备信息是否为{% kbd en0 %}，后面的{% emp 内建选项 %}是否☑️
- 以下情况需要网卡内建
  - 网卡不是en0
  - en0后面没有打勾

- 以下属于硬件支持故障 
  - 没有识别驱动网卡
  - 没有内置网卡_使用USB网卡

- 以下情况需要更换三码
  - en0且勾选还是无法登陆

## 网卡内建

1. 终端输入
{% copy open /Library/Preferences/SystemConfiguration/ %}
- 找到并删除{% kbd NetworkInterfaces.plist %}
  - 可能需要打开显示隐藏文件

2. 在系统设置偏好的”网络””里删除所有网络连接
![uG6pHc](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/uG6pHc.png)

3. 重新启动系统查看网络偏好设置
- 重新在系统设置偏好的”网络”里加所有网络连接（这条一般系统会自动完成）
- 这时候在进入打开Hackintool你会发现网卡内建已经☑️完成

4. 如果效果没有成功展现，请尝试设备内建

## 设备内建
- 此条通常用于NVMe磁盘被识别外置改内置
- 也可以内建网卡使用
- 此条我仅于oc测试过，并不确定是否支持四叶草

1. 打开Hackintool-PCIe查找该设备PCI路径
![C8I5px](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/C8I5px.png)
2. 找到对应的设备信息，鼠标右键点击他，并点击弹出选项{% kbd CopyDevicePath %}。此时剪贴板中将会出现一串设备代码

3. 将其粘贴到你的OC引导：{% emp EFI-OC-config.plist %} 文件
- 并添加参数
```
built-in   01   data
```
{% folding 使用OpenCore Configurator %}
![w6MmRE](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/w6MmRE.png)
{% endfolding %}
{% folding 使用plistedit %}
![iDcL84](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/iDcL84.png)
{% endfolding %}

4. 重启确认是否已经完成设备内建。
  - 这条成功率蛮高的。

- {% emp 如果完成上述教程，仍旧无法登陆APP Store（应用商店） %}
  - 请尝试仿冒以太网[https://ocbook.tlhub.cn/13-仿冒以太网和重置以太网BSD%20Name/](https://ocbook.tlhub.cn/13-仿冒以太网和重置以太网BSD%20Name/)
  - 10.13.6应用商店已断网！！！无解

### 洗白（换三码）
直接看图
![xDOq12](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/Ppea54.png)

### iMessage/Facetime登录异常修复
- 尝试购买白果三码，或换三码摸奖

- 联系Apple支持解决
注：以下流程由[常远部落阁](http://blog.runebalot.cn)提供
  - 建议使用购买日期未验证的序列号。
  - 不可使用绿码，白果码
  - 使用您的真实ROM地址。

1. 终端运行以下代码，运行iMessage
{% copy /System/Applications/Messages.app/Contents/MacOS/Messages %}

2. 终端窗口找到如下客户代码，并将其复制保存。
```
您目前无法在此 Mac 上登录 iMessage 信息。:  要在此 Mac 上使用 iMessage 信息，请联系 Apple 支持并提供下面的代码。

顾客代码：xxxx-xxxx-xxxx
Apple ID: xxxxxxxxxx@icloud.com
```

3.登陆Apple官网联系Apple 支持，告知你出现的问题
  - 如果他询问，就告诉他您还尝试了 RESET NVRAM、SMC 和恢复出厂设置。
  - 不问不说。
  - 通常会转接两次，

4. 他们会询问您是否是 Apple ID 的所有者，并向您登录 iCloud 的设备提供验证弹出窗口。

5. 完成设备验证，即可登录iMessage/Facetime测试

注：**弄完之后不可更换三码中的MLB**
