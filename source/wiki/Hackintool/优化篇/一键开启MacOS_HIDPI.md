---
layout: wiki
wiki: Hackintool
title: 一键开启 MacOS HIDPI
order: 203
---

## 效果与预览
这个脚本的目的是为中低分辨率的屏幕开启 HIDPI 选项，并且具有原生的 HIDPI 设置，不需要 RDM 软件即可在系统显示器设置中设置MacOS 的 dpi 机制和 win 下不一样，比如 1080p 的屏幕在 win 下有 125%、150% 这样的缩放选项，而同样的屏幕在 MacOS 下，缩放选项里只是单纯的调节分辨率，这就使得在默认分辨率下字体和 UI 看起来很小，降低分辨率又显得模糊。

同时，此脚本也可以通过注入修补后的 EDID 修复闪屏，或者睡眠唤醒后的闪屏问题，当然这个修复因人而异（如4400-4600）

脚本发布[项目地址](https://github.com/xzhih/one-key-hidpi)
![14:27-gQ9YxR](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/shaoxing/20210921/14:27-gQ9YxR.png)

## 使用教程
### 远程模式
- 在终端输入以下命令回车即可。
{% copy bash -c "$(curl -fsSL https://raw.githubusercontent.com/xzhih/one-key-hidpi/master/hidpi.sh)" %}
### 本地模式
- 下载one-key-hidpi-master项目解压,双击**hidpi.command**运行
  - [蓝奏云下载](https://shoaling.lanzoui.com/imB4Amaeete)
  - [官方项目下载](https://github.com/xzhih/one-key-hidpi)

### 使用示范
1. 打开{% kbd 打开hidpi.command %}
```

Last login: Sun Feb 28 19:33:45 on ttys000
/Users/*****Downloads/one-key-hidpi-master/hidpi.command ; exit;           
*****@*****deMacBook-Pro ~ % /Users/*****/Downloads/one-key-hidpi-master/hidpi.command ; exit;
  _    _   _____   _____    _____    _____ 
 | |  | | |_   _| |  __ \  |  __ \  |_   _|
 | |__| |   | |   | |  | | | |__) |   | |  
 |  __  |   | |   | |  | | |  ___/    | |  
 | |  | |  _| |_  | |__| | | |       _| |_ 
 |_|  |_| |_____| |_____/  |_|      |_____|
                                           
============================================

(1) 开启HIDPI
(2) 开启HIDPI(同时注入EDID)
(3) 关闭HIDPI

输入你的选择 [1~3]:
```
2. 输入你的选择。{% psw 如:2 %}
``` 
-------------------------------------
|********** 选择显示器ICON ***********|
-------------------------------------

(1) iMac
(2) MacBook
(3) MacBook Pro
(4) LG 显示器
(5) Pro Display XDR
(6) 保持原样

输入你的选择 [1~6]:
``` 
3. 选择你想模拟的的显示器ICON图标，{% psw 如：3 %}（{% u 此后需要输入密码 %}）
```
------------------------------------------
|********** 选择分辨率配置 ***********|
------------------------------------------
(1) 1920x1080 显示屏
(2) 1920x1080 显示屏 (使用 1424x802 分辨率，修复睡眠唤醒后的屏幕缩小问题)
(3) 1920x1200 显示屏
(4) 2560x1440 显示屏
(5) 3000x2000 显示屏
(6) 手动输入分辨率

输入你的选择:
```
4. 选择合适的分辨率{% psw （1？2？3？4？5？）或者自定义（6？） %}
5. 因为上面没有适合我的分辨率，故我选择自定义“6”并输入开启HIDPI的分辨率,输入密码回车键后。
```
输入你的选择: 6
输入想要开启的 HIDPI 分辨率，用空格隔开，就像这样：1680x945 1600x900 1440x810
```
6. 出现以下界面重启测试，如不开机或异常，请参考[恢复](#恢复)
```
开启成功，重启生效
首次重启开机logo会变得巨大，之后就不会了
Saving session...
...copying shared history...
...saving history...truncating history files...
...completed.
Deleting expired sessions...       8 completed.

[进程已完成]
```

## 恢复
### 命令回复
- 如果还能进系统，就再次运行命令选择选项 3 关闭 HIDPI。

### 恢复模式
- 如果使用此脚本后，开机无法进入系统，请到 **macos恢复模式**，打开**终端**。
- 这里有两种方式进行关闭，建议选**第一种**
1. 快捷恢复
 
```
ls /Volumes/           //查看你的系统盘
cd /Volumes/你的系统盘/Users/

ls                    //你可以看到所有用户的目录

cd 你的用户名

./.hidpi-disable
```

2. 手动恢复
   - 使用终端删除**Library/Displays/Contents/Resources/Overrides**下删除所有通过外部注入的显示器配置文件夹
   - 命令如下:
```
ls /Volumes/
rm -rf /Volumes/你的系统盘/Library/Displays/Contents/Resources/Overrides
```
