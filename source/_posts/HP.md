---
title: HP-ENVY 13-D025
cover: https://cdn.jsdelivr.net/gh/muzishaoxing/Picture@main/shaoxing/20210917/06:47-14152327.png
dark: true
tags:
  - 笔记本
categories:
  - 记录
abbrlink: c128ce6e
pin: true
date: 2021-04-21 20:45:00
---
## 系统检测
### 检测工具-[鲁大师]
- 软件:鲁大师5.1021.1300.108
- 时间:2021-04-04 14:24:37
- 网站:http://www.ludashi.com

### 硬件设备-[概览]

| **电脑型号**     | **HP ENVY13 D025 笔记本电脑**                       |
| :---------------- | :-------------------------------------------------- |
| **处 理 器**     | **英特尔 Core i5 6200U 2.30GHz双核**                  |
| **主板芯片**     | **惠普 80DF(笔记本芯片组)**                          |
| **核    显**     | **英特尔HD Graphics 520(128MB/惠普)**                 |
| **板载内存**     | **8GB(SK Hynix LPDDR3 1600MHz)**                       |
| **内置硬盘**     | **西部数据 WDS100T2B0B-00YS70 (1TB/固态硬盘)**                 |
| **显示器**       | **三星 SDC415A(13.3英寸)**                           |
| **声卡**         | **瑞昱@英特尔HighDefinition Audio控制器「ALC290」** |
| **网卡「更换」** | **英特尔 WiFi6 AX200 160MHz**                      |
| **黑苹果当前测试** | **正式版 Big Sur 11.6 <br/> 正式版 Monterey 12.0.1**|
| **报表更新日期** | **2021-10-06**                      |



### 系统支持
![09:59-双系统](https://cdn.jsdelivr.net/gh/muzishaoxing/Picture@main/shaoxing/20211006/09:59-%E5%8F%8C%E7%B3%BB%E7%BB%9F.png)
**操作系统测试支持**


| [![Monterey](https://cdn.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/Monterey.png)](https://www.apple.com.cn/macos/monterey-preview/) | [![Big_Sur1](https://cdn.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/Big_Sur1.png) ](https://www.apple.com.cn/macos/big-sur/) | [![Catalina](https://cdn.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/Catalina.png) ](https://www.apple.com.cn/newsroom/2019/10/macos-catalina-is-available-today/) | [![icon_58x58](https://cdn.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/Windows/icon_58x58.png)](https://www.microsoft.com/zh-cn/windows/features) | [![Windows11](https://cdn.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/Windows11.png) ](https://www.microsoft.com/zh-cn/windows/windows-11) | [![23:46-icon_58x58](https://cdn.jsdelivr.net/gh/muzishaoxing/Picture@main/shaoxing/20210909/23:46-icon_58x58.png)](https://www.chinauos.com/resource/download-home) |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|                         **Monterey**                         |                         **Big Sur**                          |                         **Catalina**                         |                        **Windows 10**                        |                        **Windows 11**                        |                           **UOS**                            |




### 功能检测
{% folding 点击查看功能检测 %}

#### 驱动正常的设备功能
| **功能**              | **依赖**                                                | **备注**                                                     |
| -------------------------  | :------------------------------------------------------ | ------------------------------------------------------------ |
| **Wi-Fi**                 |  **AirportItlwm_Monterey.kext<br/>AirportItlwm_Big_Sur.kext** | AirportItlwm_Catalina.kext<br/>AirportItlwm_Mojave.kext
| **蓝牙**                  |  **IntelBluetoothFirmware.kext<br/>蓝牙识别驱动☞**       | **Big Sur蓝牙识别:<br/>IntelBluetoothInjector.kext<br/>Monterey蓝牙识别:<br/>BlueToolFixup.kext** |
| **自带扬声器输出**        |  **AppleALC.kext**                                       |                                                              |
| **麦克风输入**            |  **AppleALC.kext**                                       |                                                              |
| **3.5mm 接口输出**        |  **AppleALC.kext**                                       |                                                              |
| **图形硬件加速**          |  **WhateverGreen.kext**                                  |                                                              |
| **电量百分比显示**        |  **SMCBatteryManager.kext**                              |                                                              |
| **CPU 电源管理**          |  **SSDT-PLUG-_PR.CPU0.aml**                              |                                       |
| **SMBIOS**          |  **MacBookPro13,2**                              |         **仿冒机型-三码请自我刷新**                                  |
| **S3_睡眠** |  **SSDT-DWAK.aml**                                       |                                                              |
| **S D读卡器**             |  **RealtekCardReader.kext<br/>RealtekCardReaderFriend.kext**                                   | **⚠️休眠后自动弹出<br/>👍重新插拔可用**                                        |
| **USB 电源属性** |  **SSDT-EC-USBX-LAPTOP.aml**                             |                                                              |
| **USB 2.0, USB 3.0**      |  **USBPorts.kext**                                       | **或“SSDT-UIAC.aml”**                                        |
| **显示器亮度调节**        |  **BrightnessKeys.kext<br/>SSDT-PNLF-SKL_KBL.aml**       |       **配合重命名PNLF更名XNLF<br/>解决OC引导Windows蓝屏**                                                       |
| **键盘与触控板手势**      |  **VoodooPS2Controller.kext**                            | **全部手势都可用**                                           |
| **🔗安卓USB共享网络**  |  **HoRNDIS.kext**                                        | **我不需要，尚未启用**                                       |
| **美化-白果鼠标**         |  **FakeAppleUSBMouse.kext**                              | **需改ID**                                                   |
| **SATA磁盘识别**          |  **CtlnaAHCIPort.kext**                                  | **仅Big Sur需要**                                            |
| **FN功能键**              |                                                          | **免驱**                                                     |
| **文件保险箱**              |                      勾选协议覆盖“Firmware Volume”                                    | **正常**                                                     |

#### 尚未测试与不可驱动的功能
| 功能     | 依赖  | 备注               |
| -------- | ----- | ------------------ |
| 指纹 | **❌** | 无法驱动 |
| 隔空投送 | **❌** | 英特尔网卡暂不支持 |
| 开机音频 | **❌** | 原因不详           |
| 开机花屏 | **⚠️**   | 一瞬闪屏           |
| 随航投屏 | **⁉️**   | 暂未测试           |
| HDMI输出 | **✅**    | 22.1.12测试正常 |



> 上述检测信息实时更新，以最新版引导为校准
{% endfolding %}
## 更新日志
{% folding 点开查看更新日志 %}
{% timeline %}

<!-- node 2022 年 01 月 11 日 -->

例行更新引导版本0.7.7正式版

更新相应驱动版本

测试HDMI输出正常！

<!-- node 2021 年 11 月 11 日 -->
升级引导版本0.7.6开发板
修复**文件保险箱**开启后无法启动

<!-- node 2021 年 10 月 30 日 -->
完美支持**Monterey**正式版
- 升级**BlueToolFixup.kext**为2.6.1开发版，修复蓝牙无法关闭
- 重新调整显卡参数，确保更好的支持
- 发布包名{% kbd Monterey正式版074 %}
  - 注:此包依旧可以正常使用Big Sur
  <!-- node 2021 年 10 月 5 日 -->
  升级OpenCore0.7.4正式版底包,更新部分驱动版本
- 因官方文档说明，修改**ext4_x64.efi**优先于**OpenLinuxBoot.efi**前加载。
- 增加驱动[RestrictEvents.kext](https://github.com/acidanthera/RestrictEvents)用于解决Monterey bate更新出错。

<!-- node 2021 年 9 月 10 日 -->
- 添加以下驱动以支持原生引导Linux
  - {% kbd OpenLinuxBoot.efi %}
  - {% kbd ext4_x64.efi %}
  - {% kbd btrfs_x64.efi %}

<!-- node 2021 年 9 月 7 日 -->
升级OpenCore0.7.3正式版底包,更新部分驱动版本
- 更换自制简约主题![23:52-20210909](https://cdn.jsdelivr.net/gh/muzishaoxing/Picture@main/shaoxing/20210909/23:52-20210909.png)
- {% del 移除原SD读卡器驱动“Sinetek-rtsx.kext” %}替换为{% u RealtekCardReader.kext+RealtekCardReaderFriend.kext %}
  - 优点: 内建SD读卡器，系统报告可查
  - 缺点: 休眠强制弹出（可热插拔恢复）{% sub 小毛病的了，不影响使用 color:light %}

<!-- node 2021 年 8 月 5 日 -->
升级OpenCore0.7.2正式版底包,更新部分驱动版本
- 替换全套网卡驱动为{% u ax200专用精简版 %}
- 调整SSDT补丁为专用补丁
  - 增加重命名PNLF renamed XNLF 
  - 解决调整后无法进入Windows
- 注意：{% u 此引导版本已无法支持Big Sur以下版本，使用Catalina及以下版本不可升级！ %}

<!-- node 2021 年 7 月 30 日 -->
- 添加英特尔无线网卡对**Monterey**支持
  1. 添加驱动“BlueToolFixup.kext”并设置限定最小内核“21.0.0“
  2. 添加设置“IntelBluetoothInjector.kext”内核上限“20.99.99”
      - *用于解决蓝牙在Big Sur与Monterey下正常工作。*
     - *如不如此操作，两个驱动会在不同的版本出现报错。。。*
  3. 添加驱动“AirportItlwm_Monterey.kext”并设置最小内核“21.0.0”
     - *用于Wi-Fi在Monterey下正常运作。*
- ![Stn0xI](https://cdn.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/Stn0xI.png)
- 添加Tools工具“CleanNvram.efi”“TpmInfo.efi”

<!-- node 2021 年 7 月 15 日 -->
- 升级OpenCore0.7.1正式版底包,更新部分驱动版本
- 调整新版主题文件夹文件架构，并添加4个主题包内置

<!-- node 2021 年 6 月 15 日 -->
- 升级OpenCore0.7.0正式版底包,更新部分驱动版本

<!-- node 2021 年 5 月 14 日 -->
- 再次修改MIsc自定义启动项绝对路径
> \Windows\Microsoft\BOOT\bootmgfw.efi”
> - 用于解决某些情况被误删！！！
> - 方便打包发布（需要同时移动BOOT文件夹到指定目录）

<!-- node 2021 年 5 月 7 日 -->
  升级OpenCore0.6.9正式版底包,更新部分驱动版本
- 修改MIsc自定义启动项绝对路径

> \EFI\Windows\Microsoft\BOOT\bootmgfw.efi”
> - 用于解决某些情况被误删！！！
- 新增SSDT-UIAC.aml锁定usb端口，让系统更稳定
  - **如非此机型务必要删除套用**

<!-- node 2021 年 4 月 8 日 -->
- 升级OpenCore0.6.8正式版底包,更新部分驱动版本

<!-- node 2021 年 3 月 2 日 -->
- 升级OC0.6.7，调整部分驱动更新，完善休眠信息
- 增加补丁：“SSDTPMCR.aml”
    - 添加缺失设备，APP9876，NVRAM相关
- 增加补丁：“SSDTSBUS.aml“
    - 修复SBUS
- 增加补丁：“SSDTDWAK.aml“
    - 修复待机睡眠功能
- 调整移动Windows系统EFI文件至oc目录下widows文件夹
    - 让你更清楚知道这是什么文件夹
- 修改MIsc自定义启动项绝对路径
> \EFI\OC\Windows\Microsoft\BOOT\bootmgfw.efi”

<!-- node 2021 年 1 月 27 日 -->
- 移动Windows系统EFI文件至oc目录下用于BIOS默认启动项为oc
- 添加MIsc自定义启动项绝对路径
> \EFI\OC\Microsoft\BOOT\bootmgfw.efi

<!-- node 2021 年 1 月 24 日 -->
- 升级OpenCore0.6.6正式版底包，更新个性图形化主题，增加图形化背景

<!-- node 2021 年 1 月 20 日 -->
- 重新定义ssdt/Kexts注释名
- 测试，检查，修复OC引导Windows

<!-- node 2021 年 1 月 10 日 -->
- 升级OpenCore0.6.5正式版底包
- 更换内核“itlwm.kext”为
    - AirportItlwm_Big_Sur.kext
    - AirportItlwm_Catalina.kext
    - AirportItlwm_Mojave.kext
    - AirportItlwm_High_Sierra.kext
    - 修复各版本原生WiFi开关使用

- 增加驱动“CPUFriend.kext与CPUFriendDataProvider.kext“增强CPU变频管理
- 增加内核“FakeAppleUSBMouse.kext”开启白果鼠标设置界面，开启更多鼠标自定义玩法（驱动需要自定义）

<!-- node 2021 年 1 月 9 日 -->
- 发现故障SD卡休眠无法识别，报错“您插入的磁盘在此电脑上不能读取”
    - 禁用S3睡眠后不再报错，但是耗电量增加。
    - 移除sd卡驱动，眼不见为净

<!-- node 2020 年 12 月 11 日 -->
- 完善系统体验，设备硬件驱动完善。
- 增加内核“Sinetekrtsx.kext”
    - 驱动内置SD卡读卡器。
- 增加内核“BrightnessKeys.kext
    - 驱动亮度调节
- 增加内核“SMCBatteryManager.kext”
    - 驱动电池电量显示
- 增加内核“itlwm.kext"
    - 驱动英特尔AX200WiFi
- 增加内核“HoRNDIS.kext“
    - 驱动手机USB共享网络
- 增加内核“USBPorts.kext”
    - 定制USB端口信息
- 增加内核“IntelBluetoothFirmware.kext”
    - 驱动英特尔蓝牙
- 增加设备属性：显卡仿冒ID“AAPL,igplatformid=00001619”驱动显卡「并修补接口信息（这些不一定通用）」
- 增加设备属性：声卡仿冒ID“layoutid=1C000000“驱动声卡（型号=ALC269/ID=28）
- 增加ACPI补丁：“SSDTPLUG.aml”开启节能五项
- 增加ACPI补丁：“SSDTPNLF.aml”驱动亮度调节快捷键

<!-- node 2021 年 7 月 30 日 -->
- 通过：https://github.com/acidanthera/OpenCorePkg
    - 下载OpenCore0.6.4正式版
- 通过：https://opencore.slowgeek.com
    - 选择架构，设置推荐OpenCore配置表参数

- 并加载核心驱动+核心补丁用于系统安装
- 核心驱动：
    - Lilu.kext
      - 仿冒核心前置驱动
    - VirtualSMC.kext
      - 虚拟SMC
    - AppleALC.kext
      - 声卡驱动
    - SMCProcessor.kext 
      - 处理器驱动
    - SMCSuperIO.kext
      - IO传感器
    - USBInjectAll.kext 
      - USB总线驱动
    - WhateverGreen.kext
      - 图形卡驱动
    - VoodooPS2Controller.kext 
      - 笔记本键盘（触摸板）驱动
- 核心补丁：
    - SSDTECUSBXLAPTOP
      - 仿冒并覆盖嵌入式控制器，并强制USB电源属性
- 附加项目：
    - 增加“CtlnaAHCIPort.kext”
      - 用于BigSur系统下识别部分SATA磁盘（我的盘需要）。
    - 勾选惠普专用内核quirks选项
      - LapicKernelPanic
    - 勾选SATA磁盘专用内核quirks选项
      - “ThirdPartyDrives”开启TRIM支持
    - 设置六代笔记本推荐SMBIOS：MacBookPro13,2及三码信息
    
- 完成上述，即可安装进系统了。
  
- 主板设置：
    - 惠普这个机型主板设置相对简单，只需要关闭安全启动即可！！！


{% endtimeline %}
{% endfolding %}


## 下载地址聚合
{% folding 下载地址 %}
- 教程合集
  - https://hackintool.vercel.app/
  - https://hackintool.netlify.app/
- 我的成品EFI：https://www.123pan.com/s/SztA-5XMmH
- 我的主题仓库: https://www.123pan.com/s/SztA-ZXMmH
- 驱动下载地址： 
  - OC底层架构更新: [OpenCorePkg](https://github.com/acidanthera/OpenCorePkg)
  - OC官方主题仓库: [OcBinaryData](https://github.com/acidanthera/OcBinaryData)
  - 核心驱动: [Lilu](https://github.com/acidanthera/Lilu)
  - SMC仿真器:[VirtualSMC](https://github.com/acidanthera/VirtualSMC/releases)
  - 显卡驱动: [WhateverGreen](https://github.com/bugprogrammer/WhateverGreen/releases)
  - 声卡驱动: [AppleALC](https://github.com/acidanthera/AppleALC)
  - 英特尔无线网卡: [itlwm](https://github.com/OpenIntelWireless/itlwm)
  - 英特尔蓝牙驱动: [IntelBluetoothFirmware](https://github.com/OpenIntelWireless/IntelBluetoothFirmware)
  - 博通网卡Wi-Fi: [AirportBrcmFixup](https://github.com/acidanthera/AirportBrcmFixup/releases)
  - 博通网卡蓝牙: [BrcmPatchRAM/BlueToolFixup](https://github.com/acidanthera/BrcmPatchRAM/releases)
  - PS2键盘触控板驱动: [VoodooPS2](https://github.com/acidanthera/VoodooPS2/releases)
  - I2C触控板驱动: [VoodooI2C](https://github.com/VoodooI2C/VoodooI2C/releases)
  - 亮度调节键: [BrightnessKeys](https://github.com/acidanthera/BrightnessKeys)
  - CPU频率定制: [CPUFriend](https://github.com/acidanthera/CPUFriend)
  - USB 端口识别: [USBInjectAll](https://github.com/daliansky/OS-X-USB-Inject-All)
  - SD读卡器驱动（可识别内建）: [RealtekCardReader](https://github.com/0xFireWolf/RealtekCardReader)+[RealtekCardReaderFriend](https://github.com/0xFireWolf/RealtekCardReaderFriend)
  - SD读卡器驱动（不识别内建）：[Sinetek-rtsx](https://github.com/cholonam/Sinetek-rtsx/releases)
  - 安卓USB共享网络: [HoRNDIS](https://github.com/jwise/HoRNDIS/releases)
  - 解除更新限制: [RestrictEvents.kext](https://github.com/acidanthera/RestrictEvents)
- ACPI补丁包：https://github.com/daliansky/OC-little
  {% endfolding %}
