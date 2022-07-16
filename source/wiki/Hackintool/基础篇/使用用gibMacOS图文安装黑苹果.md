---
layout: wiki
wiki: Hackintool
title: 使用用gibMacOS图文安装黑苹果
order: 30
---

- 众所周知，安装黑苹果较旧版本（比如10.13.6）镜像包难找或出现很多奇怪的毛病，如安装资源过期，安装包已损坏等（镜像包签名过期导致的，强制安装需要更改BIOS时间）
- 在这里，我给大家推荐一个可以不必为此项问题为难的解决方式
- 使用**gibMacOS**在**Win环境**下从**Apple官网**下载镜像制作安装盘
- 准备需求
  - **准备一台win10电脑**
  - **一个1G以上U盘**（做mac的启动盘）
  - 一个有线鼠标
  - 一个USB集线器（可插网线）
  - 一根网线
- 因为创建一个 USB 安装启动盘，很多资源在github在线获取，需要修改hosts文件达到Github下载提速（可参考知乎-gibhub加速）

## 使用教程
### 小白警告
{% emp 为了方便阅读所有截图替换为代码填写，以下代码框内容仅供阅读！别去复制没啥用！ %}
### gibMacOS与环境文件下载
- [**下载gibMacOS**](https://github.com/corpnewt/gibMacOS)
- 下图页面，点选**Download ZIP**下载，将其解压缩到某处
  - 如无法进入：{% psw 请自行科学上网 %}

![15:28-POyOoc](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/shaoxing/20210921/15:28-POyOoc.jpg)

- [备用分流版gibmacOS含py](https://www.123pan.com/s/SztA-6XMmH)
   - 此链接可以忽略，脚本会自动下载并安装，不过下载速度，让人堪忧。
- 下载后解压进入（目录不要包含中文），双击打开gibMacOS.bat批处理文件进入以下界面。

### 镜像下载
```

  ###              ###
 # Python Not Found #
###              ###

Python 3 was not found on the system or in the PATH var.

Would you like to install it now? [y/n]:
```
1. 请回复“Y”进入自动下载python，
   - 此界面是因为没有python环境，如果提前安装了不会出现此界面
```

  ###               ###
 # Installing Python #
###               ###

Gathering info from https://www.python.org/downloads/windows/...
Parsing for latest...
Found Python 3.9.2 -  Downloading...
```
2. 正在下载Python 3.9.2如果下载速度慢，或卡住请手动下载安装分流版！
3. 进入以下界面自动下载Catalog （如果卡住不动，请关闭代理）
```

  #######################################################
 #                Downloading Catalog                  #
#######################################################

Currently downloading publicrelease catalog from

https://swscan.apple.com/content/catalogs/others/index-10.15-10.14-10.13-10.12-10.11-10.10-10.9-mountainlion-lion-snowleopard-leopard.merged-1.sucatalog

Downloaded 6.90 MB of 6.90 MB (100.00%)
```
4. catalog下载完成后进入系统下载选择交互
   -  输入下载的系统版本（菜单）对应的索引编号回车即可自动进行下载（切换）
```

  #######################################################
 #                     gibMacOS                        #
#######################################################

Available Products:

1. Unknown Unknown
- 071-05432 - Added 2021-02-15 18:03:05 - 12.21 GB
2. macOS Catalina 10.15.7 (19H15)
- 001-68446 - Added 2020-11-11 17:48:09 - 8.75 GB
3. macOS Catalina 10.15.7 (19H4)
- 001-57224 - Added 2020-10-27 17:28:13 - 8.75 GB
4. macOS Catalina 10.15.7 (19H2)
- 001-51042 - Added 2020-09-24 17:09:31 - 8.75 GB
5. macOS Catalina 10.15.6 (19G2021)
- 001-36801 - Added 2020-08-12 20:04:02 - 8.75 GB
6. macOS Catalina 10.15.6 (19G2006)
- 001-36735 - Added 2020-08-06 23:39:24 - 8.75 GB
7. macOS Catalina 10.15.5 (19F2200)
- 001-15219 - Added 2020-06-15 18:52:41 - 8.74 GB
8. Unknown Unknown
- 001-04366 - Added 2020-05-04 15:32:04 - 8.75 GB
9. macOS Catalina 10.15.3 (19D2064)
- 061-86291 - Added 2020-03-23 21:41:00 - 8.69 GB
10. macOS Mojave 10.14.4 (18E2034)
- 041-88800 - Added 2019-10-23 14:41:18 - 6.53 GB
11. Install macOS High Sierra Beta 10.13.5 (17F66a)
- 041-90855 - Added 2019-10-23 14:41:18 - 5.69 GB
12. macOS High Sierra 10.13.6 (17G66)
- 041-91758 - Added 2019-10-19 18:19:55 - 5.71 GB
13. macOS Mojave 10.14.6 (18G103)
- 061-26589 - Added 2019-10-14 20:51:08 - 6.52 GB
14. macOS Mojave 10.14.5 (18F2059)
- 061-26578 - Added 2019-10-14 20:38:26 - 6.52 GB

M. Change Max-OS Version (Currently 10.15)
C. Change Catalog (Currently publicrelease)
I. Only Print URLs (Currently False)
S. Set Current Catalog to SoftwareUpdate Catalog
L. Clear SoftwareUpdate Catalog
R. Toggle Recovery-Only (Currently Off)
U. Show Catalog URL
Q. Quit

Please select an option:
```
5. 这里讲的是恢复分区版镜像安装{% u 所以我们选择菜单“**R**”即“**Toggle Recovery-Only (Currently Off**)“进入切换仅恢复模式。 %}
   -  M：更改Max-0s版本(当前为10.15)
   -  C：更改目录(当前发布)
   -  I：仅打印URL(当前为Fatse)
   -  S：将当前目录设置为软件重新更新目录
   -  L：清除软件重新更新目录
   -  R：切换恢复-0nty(当前关闭)
   -  U：显示目录URL
   -  Q：退出
```

  #######################################################
 #                    Parsing Data                     #
#######################################################

Re-scanning products after url preference toggled...
```
6. 切换中。。。请稍后！
```
  #######################################################
 #                     gibMacOS                        #
#######################################################

Available Products:

1. macOS Mojave Security Update 2021-001 10.14.6 (18G8012)
- 001-96205 - Added 2021-02-09 19:43:25 - 482.09 MB
2. macOS Catalina Security Update 2021-001 10.15.7 (19H512)
- 001-93719 - Added 2021-02-09 19:41:03 - 500.53 MB
3. macOS Mojave Security Update 2021-002 10.14.6 (18G8022)
- 071-05177 - Added 2021-02-09 19:39:25 - 482.18 MB
4. macOS Catalina 10.15.7 Supplemental Update 10.15.7 (19H524)
- 071-05425 - Added 2021-02-09 19:27:40 - 500.48 MB
5. Security Update 2020-007 10.14.6 (18G7016)
- 001-88083 - Added 2021-01-15 22:20:31 - 482.15 MB
6. Security Update 2020-001 10.15.7 (19H114)
- 001-88090 - Added 2021-01-15 22:20:11 - 500.45 MB
7. Security Update 2020-006 10.13.6 (17G14042)
- 001-72525 - Added 2020-11-12 19:33:55 - 486.12 MB
8. Security Update 2020-006 10.14.6 (18G6042)
- 001-72538 - Added 2020-11-12 19:33:00 - 482.23 MB
9. macOS Catalina 10.15.7 (19H15)
- 001-68446 - Added 2020-11-11 17:48:09 - 500.66 MB - FULL Install
10. macOS Catalina 10.15.7 Supplemental Update 10.15.7 (19H15)
- 001-73001 - Added 2020-11-05 18:13:06 - 500.66 MB
11. macOS Catalina 10.15.7 Update 10.15.7 (19H15)
- 001-57230 - Added 2020-11-05 18:12:55 - 500.66 MB
12. macOS Catalina 10.15.7 (19H4)
- 001-57224 - Added 2020-10-27 17:28:13 - 500.52 MB - FULL Install
13. macOS Catalina 10.15.7 Update 10.15.7 (19H2)
- 001-51032 - Added 2020-10-15 17:09:29 - 500.59 MB
14. macOS Catalina 10.15.7 Update 10.15.7 (19H2)
- 001-51037 - Added 2020-10-15 17:09:15 - 500.59 MB
15. Security Update 2020-005 10.14.6 (18G6032)
- 001-48327 - Added 2020-10-01 22:08:39 - 482.26 MB
16. Security Update 2020-005 10.13.6 (17G14033)
- 001-48382 - Added 2020-09-24 17:16:25 - 486.14 MB
17. macOS Catalina 10.15.7 (19H2)
- 001-51042 - Added 2020-09-24 17:09:31 - 500.59 MB - FULL Install
18. macOS Catalina 10.15.6 Supplemental Update 10.15.6 (19G2021)
- 001-36816 - Added 2020-09-04 17:10:43 - 500.45 MB
19. macOS Catalina 10.15.6 Update 10.15.6 (19G2021)
- 001-22632 - Added 2020-09-04 17:10:19 - 500.45 MB
20. macOS Catalina 10.15.6 Update 10.15.6 (19G2021)
- 001-22626 - Added 2020-09-04 17:09:38 - 500.45 MB
21. Security Update 2020-004 10.13.6 (17G14019)
- 001-08570 - Added 2020-09-04 17:09:02 - 486.03 MB
22. Security Update 2020-004 10.14.6 (18G6020)
- 001-26311 - Added 2020-09-04 17:08:26 - 482.16 MB
23. macOS 10.15.6 Update 10.15.6 (19G73)
- 061-94461 - Added 2020-09-04 17:07:35 - 500.42 MB
24. macOS 10.15.6 Update 10.15.6 (19G73)
- 061-94457 - Added 2020-09-04 17:06:00 - 500.42 MB
25. macOS Catalina 10.15.5 Update 10.15.5 (19F101)
- 001-12343 - Added 2020-09-04 17:05:08 - 500.23 MB
26. macOS Catalina 10.15.5 Update 10.15.5 (19F101)
- 001-12341 - Added 2020-09-04 17:04:24 - 500.23 MB
27. macOS Catalina 10.15.5 Supplemental Update 10.15.5 (19F101)
- 001-12339 - Added 2020-09-04 17:03:54 - 500.23 MB
28. macOS Catalina 10.15.6 (19G2021)
- 001-36801 - Added 2020-08-12 20:04:02 - 500.45 MB - FULL Install
29. macOS Catalina 10.15.6 (19G2006)
- 001-36735 - Added 2020-08-06 23:39:24 - 500.45 MB - FULL Install
30. macOS Catalina 10.15.5 (19F2200)
- 001-15219 - Added 2020-06-15 18:52:41 - 500.36 MB - FULL Install
31. macOS Catalina 10.15.5 Supplemental Update 10.15.5 (19F2200)
- 061-78585 - Added 2020-06-15 17:00:03 - 500.36 MB
32. macOS Catalina 10.15.4 (19E2269)
- 001-04366 - Added 2020-05-04 15:32:04 - 500.02 MB - FULL Install
33. macOS Catalina 10.15.3 (19D2064)
- 061-86291 - Added 2020-03-23 21:41:00 - 499.55 MB - FULL Install
34. macOS Mojave 10.14.6 Supplemental Update 2 10.14.6 (18G103)
- 061-41417 - Added 2019-10-24 18:25:52 - 481.99 MB
35. macOS 10.14.6 Update 10.14.6 (18G103)
- 061-41421 - Added 2019-10-24 18:24:51 - 481.99 MB
36. macOS 10.14.6 Update 10.14.6 (18G103)
- 061-41419 - Added 2019-10-24 18:22:50 - 481.99 MB
37. MacBook Pro Supplemental Update 10.14.5 (18F203)
- 041-88834 - Added 2019-10-23 17:12:57 - 481.55 MB
38. macOS Mojave 10.14.4 (18E2034)
- 041-88800 - Added 2019-10-23 14:41:18 - 491.50 MB - FULL Install
39. Install macOS High Sierra Beta 10.13.5 (17F66a)
- 041-90855 - Added 2019-10-23 14:41:18 - 486.92 MB - FULL Install
40. macOS High Sierra 10.13.6 (17G66)
- 041-91758 - Added 2019-10-19 18:19:55 - 487.84 MB - FULL Install
41. macOS 10.14.2 Update Combo 10.14.2 (18C54)
- 041-88764 - Added 2019-10-15 20:19:46 - 487.16 MB
42. macOS Mojave 10.14.6 (18G103)
- 061-26589 - Added 2019-10-14 20:51:08 - 481.99 MB - FULL Install
43. macOS Mojave 10.14.5 (18F2059)
- 061-26578 - Added 2019-10-14 20:38:26 - 481.64 MB - FULL Install
44. macOS 10.14.2 Update 10.14.2 (18C54)
- 041-91742 - Added 2019-10-09 19:42:38 - 487.16 MB

M. Change Max-OS Version (Currently 10.15)
C. Change Catalog (Currently publicrelease)
I. Only Print URLs (Currently False)
S. Set Current Catalog to SoftwareUpdate Catalog
L. Clear SoftwareUpdate Catalog
R. Toggle Recovery-Only (Currently On)
U. Show Catalog URL
Q. Quit
```
7. 进入仅恢复镜像模式，所出现系统版本尾部带有关字“**FULL Install**”即是恢复分区镜像安装包，输入对应的索引编号即可进入下载！
```
17. macOS Catalina 10.15.7 (19H2)
- 001-51042 - Added 2020-09-24 17:09:31 - 500.59 MB - FULL Install
```
8. 例如：我选择下载Catalina 10.15.7 (19H2)则输入对应索引编号“17”系统会自动进入下载。
```

  #######################################################
 #              Downloading File 1 of 1                #
#######################################################

Downloading RecoveryHDMetaDmg.pkg for 001-68446 - 10.15.7 macOS Catalina...

Downloaded 103.81 MB of 500.66 MB (20.53%)
```
9. 开始下载，下载进度条跑到（100%）会自动跳到下载成功界面
```

  #######################################################
 #                 Downloaded 1 of 1                   #
#######################################################

Succeeded:
RecoveryHDMetaDmg.pkg

Failed:
None

Files saved to:
  C:\Users\******\Desktop\gibMacOS-master\macOS Downloads\publicrelease\001-51042 - 10.15.7 macOS Catalina

Press [enter] to return...
```
10. 出现此界面表示下载成功，此时可以关闭gibMacOS.batgibMacOS.bat窗口了，此脚本暂时已经完成使用。

### 创建Mac Recovery启动盘
1. 此时需要{% del 关闭gibMacOS.bat %}打开**MakeInstall.bat**创建Mac Recovery启动盘
```

  #######################################################
 #              Checking Required Tools                #
#######################################################

Couldn't locate ddrelease64.exe - downloading...
```
2. 正在下载关键性组件。
```

#######################################################
#             Potential Removable Media               #
#######################################################

!WARNING!  This list includes both Removable AND
!WARNING!  Unknown disk types.  Be ABSOLUTELY sure
!WARNING!  before selecting a disk!

1. SDXC Card - 62.54 GB (Removable)
   0. I: (SD) exFAT - 62.53 GB
2. General UDisk USB Device - 16.04 GB (Removable)
   0. F: (BOOT) FAT32 - 205.52 MB

Q. Quit

Usage: [drive number][option (only one allowed)] r[Clover revision (optional)]
  (eg. 1B r5092)
  Options are as follows with precedence B > E > U > G:
    B = Only install the boot manager to the drive's first partition.
    O = Use OpenCore instead of Clover.
    E = Sets the type of the drive's first partition to EFI.
    U = Similar to E, but sets the type to Basic Data (useful for editing).
    G = Format as GPT (default is MBR).
    D = Used without a drive number, toggles showing all disks (currently DISABLED).

Please select a disk or press [enter] with no options to refresh:
```
3. 扫描并识别U盘创建索引
```

1. SDXC Card - 62.54 GB (Removable)
   0. I: (SD) exFAT - 62.53 GB
2. General UDisk USB Device - 16.04 GB (Removable)
   0. F: (BOOT) FAT32 - 205.52 MB
```
4. 这里是扫面到的U盘信息。选择对应索引值进入下一步，
   - PS：此处可以直接输入索引值+O，写入U盘并替换默认引导为 OpenCore
   - 如：2O（是字母O。不是数字0，不区分大小写）
```

#######################################################
#          Erase General UDisk USB Device             #
#######################################################

2. General UDisk USB Device - 16.04 GB (Removable)

If you continue - THIS DISK WILL BE ERASED
ALL DATA WILL BE LOST AND ALL PARTITIONS WILL
BE REMOVED!!!!!!!

Continue? (y/n):
```
5. 是否继续
   -  继续请回复：Y {% sub 此磁盘将被擦除，所有数据都将丢失，所有分区都将被除名！ %}
   -  返回请回复：N {% sub 返回上一步 %}
6. 选择Y后进入

```
  #######################################################
 #               Erasing With DiskPart                 #
#######################################################

Using MBR...

Microsoft DiskPart 版本 10.0.19041.610

Copyright (C) Microsoft Corporation.
在计算机上: 少星

磁盘 2 现在是所选磁盘。

DiskPart 成功地清除了磁盘。

DiskPart 已将所选磁盘成功地转更换为 MBR 格式。

DiskPart 成功地创建了指定分区。


0 百分比已完成
```
7. 正在创建启动盘分区
```

#######################################################
#              Select Recovery Package                #
#######################################################

2. General UDisk USB Device - 16.04 GB (Removable)

M. Main Menu
Q. Quit

Please paste the recovery update pkg path to extract:
```
8. 这时候将下载好的镜像安装包路径复制并填写进去回车键下一步
9. 可通过右上角搜索pkg查找到文件所在位置
![16:04-KNbUfB](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/shaoxing/20210921/16:04-KNbUfB.jpg)
10. 其他方式
   - 方式1：点选RecoveryHDMetaDmg.pkg后按住shift键+鼠标右键，列表会新增复制为路径选项
   - 方式2:点选后鼠标右键右键-属性-安全-对象名称
   - （获得文件路径方式有很多种，根据自己所知，本方式只是举例说明）
![16:05-rWS1Ym](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/shaoxing/20210921/16:05-rWS1Ym.jpg)

11.将其复制，如：

```
C:\Users\******\Desktop\gibMacOS-master\macOS Downloads\publicrelease\001-51042 - 10.15.7 macOS Catalina\RecoveryHDMetaDmg.pkg

```
12. 填写后回车进入下一步
```

  #######################################################
 #              Copying Image To Drive                 #
#######################################################

Image: C:\Users\******\AppData\Local\Temp\tmpquddq8yk\4.hfs

Disk 2. General UDisk USB Device - 16.04 GB (Removable)

C:\Users\******\Desktop\gibMacOS-master\Scripts\ddrelease64.exe if=C:\Users\26278\AppData\Local\Temp\tmpquddq8yk\4.hfs of=\\?\Device\Harddisk2\Partition2 bs=8M --progress

This may take some time!
```
13. 正在将镜像恢复到驱动器，这可能需要点时间。（请等待）
```

  #######################################################
 #            Installing Clover - Latest               #
#######################################################

Gathering info...
- Checking https://api.github.com/repos/dids/clover-builder/releases
- Got CloverISO-5122.tar.lzma
Downloading...
Downloaded 2.54 MB of 2.54 MB (100.00%)
Extracting CloverISO-5122.tar.lzma...
Extracting CloverISO-5122.tar...
Extracting EFI from Clover-5122-X64.iso...
Extracting boot0af from Clover-5122-X64.iso...
Extracting boot1f32alt from Clover-5122-X64.iso...
Extracting boot6 from Clover-5122-X64.iso...
Copying EFI folder to F:/EFI...
Copying boot6 to F:/boot...
Updating the MBR with boot0af...
Updating the PBR with boot1f32alt...
Cleaning up...

Done.

Press [enter] to return to the main menu...
```

14. 已经写好启动盘，此时重新打开会看到U盘分区名称变成BOOT打开包含

| EFI  | 引导底包（默认四叶草） |
| ---| ---------------------|
| boot | 模拟UEFI启动           |

15. 回车>返回上一步后>输入O可切换底包为最新版OpenCore
   - O = Use OpenCore instead of Clover.
   - 选择oc引导而不是四叶草
{% emp 注：底包不能直接使用需要根据你的设备进行配置并加载驱动！ %}
{% emp 注：目前OpenCore支持率大势所趋，如自制引导请选用OpenCore %}
{% emp 推荐自带引导写入！！！ %}

## 教程推荐
- 如果你有现成的EFI文件直接替换即可，如果没有你可能需要以下内容：
- OpenCore详解：https://blog.daliansky.net/OpenCore-BootLoader.html
- OpenCore配置视频版
  - 上集https://www.bilibili.com/video/BV1854y1S7fs
  - 下集https://www.bilibili.com/video/BV1Xa4y1E7AU
- 网卡驱动合集：https://mp.weixin.qq.com/s/s7HgTlHzhbUwLAHxaKTMAA
- 通用EFI架构包：https://download.shaoxingshare.com/t/VaEvV5eBGz
- 黑苹果长期维护机型整理清单：https://blog.daliansky.net/Hackintosh-long-term-maintenance-model-checklist.html

