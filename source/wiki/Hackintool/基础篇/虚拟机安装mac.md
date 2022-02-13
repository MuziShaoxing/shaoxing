---
layout: wiki
wiki: Hackintool
title: 虚拟机安装MAC
order: 24
---
> **版权©️声明 : 本文章出自[catowen](https://catowen.top)
------------
OCC是opencore的可视化编辑器，而其需要macOS的环境，本篇将讲述在VM下虚拟化macOS安装OCC的方法

[![VMware Logo](https://www.vmware.com/etc/clientlibs/vmwaredevapp/clientlib-nav-redesign/images/vm-logo.png)](https://www.vmware.com/etc/clientlibs/vmwaredevapp/clientlib-nav-redesign/images/vm-logo.png)



# 介绍OCC

OCC，全称[OpenCore Configurator](https://mackie100projects.altervista.org/opencore-configurator/)是个第三方可视化编辑器，目前测试版已经（包括汉化）更新到最新的0.6.1了，并且十分稳定，但只能在macOS下使用，而另一个可视化编辑器[QtOpencoreConfig](https://github.com/ic005k/QtOpenCoreConfig/releases)虽然支持Windows，但由于刚刚发布不久，稳定性仍然持怀疑态度，所以OCC目前是最好的可视化编辑器。

# 虚拟化macOS

| 需要的工具/应用 | 备注                                                         |
| --------------- | ------------------------------------------------------------ |
| unlocker        | 使VM可以安装macOS                                            |
| VMware          | 别告诉我你没有                                               |
| cdr镜像         | [Big SurB1的cdr镜像](https://dl2.lipf.tech/1/WWDC/2020/macOS Big Sur) |

## 破解VMware

在unlock文件夹里管理员运行**win-install.cmd**，最好和VM放在一个文件夹里，然后等它自己完成

## 新建虚拟机

和Windows一样，记得选macOS

## 安装

安装这里有坑，记得打开虚拟机根目录的后缀为VMX的文件，文本编辑器打开，添加：



Code



```
checkpoint.vmState = ""
tools.remindInstall = "FALSE"
smbios.reflectHost = "TRUE"
hw.model = "iMac15,1"
board-id = "Mac-42FD25EABCABB274"
```

这样磁盘就不会报错成灰色的了

# 优化

dock动画从神奇动画改成缩放动画（GPU不行）

辅助功能选择降低透明度（还是GPU不行）

# 安装OCC

扔进去之后直接双击会报错，右键选择打开，进入