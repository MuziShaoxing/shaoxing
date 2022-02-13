---
layout: wiki
wiki: Hackintool
title: 黑苹果 CPU 管理驱动（开启CPU变频）
order: 202
---

> 版权©️声明 : 本页出自[[少星部落阁](https://shaoxing.vercel.app)]**已删除文档备份**
------------
## 序章

我们知道苹果电脑不同的机型ID会使睿频的数据不同。

- 例如，i9-9900k 在 iMac19,1 机型中，睿频范围一般是 1.3GHz — 5.0GHz，
- 但在 MacPro7,1 中是 2.0GHz — 5.0GHz。

今天就主要讲解黑苹果下如何生成 macOS 所需要的CPU睿频性能管理驱动。

**CPUFriend.kext** 是一款用于管理CPU的驱动程序，是**Lilu.kext**的一个插件，用于提供动态电源管理数据，主要解决无法睿频的问题。

在配合**电源管理数据**、**机型ID**、**睿频配置**的情况下，可以实现对“**macOS CPU性能**”的调整。但是单独使用 **CPUFriend.kext** 并不会有任何效果，需要通过自己电脑生成 **CPUFriendDataProvider.kext**使用。

![19:51-640](https://cdn.jsdelivr.net/gh/muzishaoxing/picture@main/shaoxing/20220116/19:51-640.webp)

这类教程网上有很多，大多数都操作比较繁琐，让作为小白的我头疼欲裂。

恰逢偶然，我得到了一种一键式生成CPUFriendDataProvider.kext的脚本，特写出了教程予以分享！

## 特别注意

1. 此教程错误生成可能导致CPU异常，请尽量多的阅读相关文档再进行操作！
2. 在运行此教程脚本前，请确保已经你已经选择合适的机型并注入三码！
3. 关于机型适配选择此处不予讲解，请自行百度。
4. 以下代码为展示作用，切勿无脑复制
5. 途中代码中“***”为个人信息隐藏！！！



## 操作教程

首先下载所需脚本：[one-key-cpufriend-main](https://github.com/stevezhengshiqi/one-key-cpufriend)

- 脚本作者：stevezhengshiqi（葫芦娃）

![20:37-2YXE5y](https://cdn.jsdelivr.net/gh/muzishaoxing/picture@main/shaoxing/20220116/20:37-2YXE5y.png)

解压后得到以下文件

![20:37-22](https://cdn.jsdelivr.net/gh/muzishaoxing/picture@main/shaoxing/20220116/20:37-22.webp)

|         文件名          |    作用    |
| :---------------------: | :--------: |
|  one-key-cpufriend.sh   | 英文版脚本 |
| one-key-cpufriend_cn.sh | 中文版脚本 |

1. 根据你擅长的“语种“选择其中一个打开终端并将其拖入（以下以中文版为例）

![20:13-not26j](https://cdn.jsdelivr.net/gh/muzishaoxing/picture@main/shaoxing/20220116/20:13-not26j.png)

```
  ____   ____    _   _   _____   ____    ___   _____   _   _   ____ 
 / ___| |  _ \  | | | | |  ___| |  _ \  |_ _| | ____| | \ | | |  _ \ 
| |     | |_) | | | | | | |_    | |_) |  | |  |  _|   |  \| | | | | | 
| |___  |  __/  | |_| | |  _|   |  _ <   | |  | |___  | |\  | | |_| | 
 \____| |_|      \___/  |_|     |_| \_\ |___| |_____| |_| \_| |____/ 

你的board-id是 Mac-66E35819EE2D0D05
=====================================================================

```

2. 确认**board-id**，并输入密码进入自动下载

```
----------------------------------------------------------------------
|* 正在下载CPUFriend，源自github.com/acidanthera/CPUFriend @PMHeart *|
----------------------------------------------------------------------
如果下载速度慢，请自行百度（外网下载慢怎么办）
```

```
------------------------------
|****** 选择低频率模式 ******|
------------------------------
(1) 1200/1300mhz (保持不变)
(2) 800mhz (低负载下更省电)
(3) 自定义
你想选择哪个选项? (1/2/3)
```

3. 根据你需要的选项进行选择，我这边选择“**2**”

```
----------------------------
|****** 选择性能模式 ******|
----------------------------
(1) 最省电模式
(2) 平衡电量模式 (默认)
(3) 平衡性能模式
(4) 高性能模式
你想选择哪个模式? (1/2/3/4)
```

4. 同上根据自己的需求，我选择“**4**”高性能模式
   - **回车便会自动生成，并放置桌面**

```
正在生成CPUFriendDataProvider.kext
[ OK ]生成完成

正在清理临时文件
Password: # 输入密码清除临时文件
```

5. 输入密码清除临时文件。

```
[ OK ]清理完成

[ OK ]脚本运行结束, 请把桌面上的 CPUFriend 和 CPUFriendDataProvider
Clover: 放入 /CLOVER/kexts/Other/ 或者 L/E/ 路径下
OC: 放入 /OC/Kexts/ 并添加 README_CN 中的补丁到 config.plist - Kernel - Add
```

6. 这时候你就可以在桌面看到生成的两个文件

![20:48-xABE3f](https://cdn.jsdelivr.net/gh/muzishaoxing/picture@main/shaoxing/20220116/20:48-xABE3f.png)

7. 脚本运行结束, 请把桌面上的 **CPUFriend** 和 **CPUFriendDataProvider**进行加载。

- Clover:放入 {% emp /CLOVER/kexts/Other/ 或者 L/E/ 路径下 %}

- OpenCore: 放入 {% emp /OC/Kexts/  %}并添加 到 {% emp config.plist - Kernel - Add %}