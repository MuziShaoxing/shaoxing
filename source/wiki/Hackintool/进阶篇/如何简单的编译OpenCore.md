---
layout: wiki
wiki: Hackintool
title: 进阶篇-如何简单的编译OpenCore
order: 606
---
> 版权©️声明 : 本文章[神楽小白(GZ小白)的部落阁 ](https://blog.gzxiaobai.cn)
------------

**1、编译之前，请确保电脑里安装了 Command Line Tools，安装方法：**


终端执行：**sudo xcode-select --install**
如果因为一些不可抗力出现下载失败的问题，请尝试去苹果官网手动下载安装。

P.S.安装过 Xcode 的朋友无需安装 Command Line Tools；同时安装过正式版和 Beta 版 Xcode 的朋友，可以通过如下命令选择目标 Tools，**如果没有请忽略本条**。
在终端执行：sudo xcode-select -s /Applications/Xcode-beta.app/Contents/Developer

2、编译最新版 OC：
终端执行：{% copy cd /Users/你的用户名/Desktop/ %}
终端执行：{% copy git clone https://github.com/acidanthera/OpenCorePkg.git %}
终端执行：{% copy cd OpenCorePkg %}
终端执行：{% copy ./macbuild.tool %}

然后等待一大串的东西，选YES就行！等待编译完就好。

最后去路径 OpenCorePkg/UDK/Build/OpenCorePkg/RELEASE_XCODE5/X64/ 路径拷贝 OpenCore-x.x.x-RELEASE.zip 至桌面备用。

3、编译所需 efi 文件：

步骤跟上面一样

终端执行：{% copy cd /Users/你的用户名/Desktop/ %}
终端执行：{% copy git clone https://github.com/acidanthera/AppleSupportPkg.git %}
终端执行：{% copy cd AppleSupportPkg %}
终端执行：{% copy ./macbuild.tool %}

4、到此为止，我们得到如下两个文件：

![](https://i.loli.net/2021/05/02/L1uNPWqwBhIZ52K.png)

解压 OpenCore-x.x.x-RELEASE 获取 BOOT、OC 文件夹。解压 AppleSupport-x.x.x-RELEASE.zip 获得所需 efi 文件。

加入博主的Hackintosh交流群：**679838716**