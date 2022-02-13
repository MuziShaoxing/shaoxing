---
layout: wiki
wiki: Hackintool
title: 使用 OpenCore 引导黑苹果
order: 27
---
> 版权©️声明 : 本文章出自**Xjn´s Blog**文章：[使用 OpenCore 引导黑苹果](https://blog.xjn819.com/post/opencore-guide.html)
------------
## 简介

Opencore引导的相关设置，无聊更新，慢更。

------

## 阅读

- [Opencore Vanilla Desktop Guide](https://khronokernel-2.gitbook.io/opencore-vanilla-desktop-guide/)
- [Getting Started With OpenCore](https://github.com/khronokernel/Getting-Started-With-OpenCore)

- [精解OpenCore](https://blog.daliansky.net/OpenCore-BootLoader.html)

------

## 软件下载

- Xcode （从 App Store 或 [Apple Developer](https://developer.apple.com/) 下载)
- [ProperTree](https://github.com/corpnewt/ProperTree) 最新推荐的 config 编辑器
- [OpenCore](https://github.com/acidanthera/OpenCorePkg/releases)（官方稳定版本）
- [Hackintool](http://headsoft.com.au/download/mac/Hackintool.zip)
- [MaciASL](https://blog.xjn819.com/wp-content/uploads/2019/10/MaciASL.zip)
- [宪武大大oc部件](https://github.com/daliansky/OC-little)
- [gfxutil](https://github.com/acidanthera/gfxutil/releases)

------

## 更新日记

<details open="" style="box-sizing: border-box;"><summary style="box-sizing: border-box; display: list-item; cursor: pointer;"><font color="red" style="box-sizing: border-box;">点击查询帖子最近更新</font></summary><h3 id="2021-08-03" style="box-sizing: border-box; margin-top: 18px !important; margin-bottom: 15px; font-family: inherit; font-weight: 600; line-height: 1.5; color: rgb(50, 50, 93); font-size: 22px;"><a href="https://blog.xjn819.com/post/opencore-guide.html#2021-08-03" class="headerlink" title="2021-08-03" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;"></a>2021-08-03</h3><p style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem; font-size: 1rem; font-weight: normal; line-height: 1.8; word-wrap: break-word;">适配OpenCore 0.7.2</p><ul style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem;"><li style="box-sizing: border-box;">增加ACPI/Quirk/SyncTableIds</li><li style="box-sizing: border-box;">增加Kernel/Scheme/CustomKernel</li><li style="box-sizing: border-box;">增加UEFI/AppleInput/GraphicsInputMirroring<span class="Apple-converted-space">&nbsp;</span></li></ul><h3 id="2021-06-13" style="box-sizing: border-box; margin-top: 18px !important; margin-bottom: 15px; font-family: inherit; font-weight: 600; line-height: 1.5; color: rgb(50, 50, 93); font-size: 22px;"><a href="https://blog.xjn819.com/post/opencore-guide.html#2021-06-13" class="headerlink" title="2021-06-13" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;"></a>2021-06-13</h3><ul style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem;"><li style="box-sizing: border-box;">补充修改Config/Misc/Boot/PickerMode</li><li style="box-sizing: border-box;">补充修改Config/Misc/Boot/PickerVariant</li><li style="box-sizing: border-box;"><a target="_blank" rel="noopener" href="https://github.com/acidanthera/OcBinaryData" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;">请同步更新OcBinaryData!</a></li></ul><h3 id="2021-06-12" style="box-sizing: border-box; margin-top: 18px !important; margin-bottom: 15px; font-family: inherit; font-weight: 600; line-height: 1.5; color: rgb(50, 50, 93); font-size: 22px;"><a href="https://blog.xjn819.com/post/opencore-guide.html#2021-06-12" class="headerlink" title="2021-06-12" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;"></a>2021-06-12</h3><ul style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem;"><li style="box-sizing: border-box;">增加Config/Kernel/Quirks/ProvideCurrentCpuInfo</li><li style="box-sizing: border-box;">增加Config/Misc/Security/AllowToggleSip</li><li style="box-sizing: border-box;">增加Config/Misc/Tools/Flavour</li><li style="box-sizing: border-box;">增加Config/Misc/Tools/RealPath</li><li style="box-sizing: border-box;">增加Config/Misc/Tools/TextMode</li><li style="box-sizing: border-box;">增加Config/NVRAM/Add/ForceDisplayRotationInEFI</li><li style="box-sizing: border-box;">增加Config/PlatformInfo/Generic/AdviseFeatures</li><li style="box-sizing: border-box;">删除Config/PlatformInfo/Generic/AdviseWindows</li><li style="box-sizing: border-box;">修改Config/UEFI/Output/GopPassThrough</li><li style="box-sizing: border-box;">增加Config/UEFI/ProtocolOverrides/AppleEg2Info</li><li style="box-sizing: border-box;"><a target="_blank" rel="noopener" href="https://github.com/acidanthera/OcBinaryData" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;">请同步更新OcBinaryData!</a></li></ul><h3 id="2021-06-07" style="box-sizing: border-box; margin-top: 18px !important; margin-bottom: 15px; font-family: inherit; font-weight: 600; line-height: 1.5; color: rgb(50, 50, 93); font-size: 22px;"><a href="https://blog.xjn819.com/post/opencore-guide.html#2021-06-07" class="headerlink" title="2021-06-07" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;"></a>2021-06-07</h3><ul style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem;"><li style="box-sizing: border-box;">因问题比较严重，更新Kernel/quirks/SetApfsTrimTimeout的说明。</li></ul><h3 id="2021-05-06" style="box-sizing: border-box; margin-top: 18px !important; margin-bottom: 15px; font-family: inherit; font-weight: 600; line-height: 1.5; color: rgb(50, 50, 93); font-size: 22px;"><a href="https://blog.xjn819.com/post/opencore-guide.html#2021-05-06" class="headerlink" title="2021-05-06" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;"></a>2021-05-06</h3><p style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem; font-size: 1rem; font-weight: normal; line-height: 1.8; word-wrap: break-word;">适配OpenCore 0.6.9</p><ul style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem;"><li style="box-sizing: border-box;">修改Config/UEFI/AppleInput/CustomDelays</li><li style="box-sizing: border-box;">修改Config/UEFI/AppleInput/KeyInitialDelay</li><li style="box-sizing: border-box;">修改Config/UEFI/AppleInput/KeySubsequentDelay</li><li style="box-sizing: border-box;">增加Config/UEFI/Quirks/EnableVectorAcceleration</li><li style="box-sizing: border-box;">增加Config/UEFI/Quirks/ForgeUefiSupport</li><li style="box-sizing: border-box;">增加Config/UEFI/Quirks/ReloadOptionRoms</li></ul><h3 id="2021-04-15" style="box-sizing: border-box; margin-top: 18px !important; margin-bottom: 15px; font-family: inherit; font-weight: 600; line-height: 1.5; color: rgb(50, 50, 93); font-size: 22px;"><a href="https://blog.xjn819.com/post/opencore-guide.html#2021-04-15" class="headerlink" title="2021-04-15" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;"></a>2021-04-15</h3><p style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem; font-size: 1rem; font-weight: normal; line-height: 1.8; word-wrap: break-word;">适配OpenCore 0.6.8</p><ul style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem;"><li style="box-sizing: border-box;"><a target="_blank" rel="noopener" href="https://github.com/acidanthera/OcBinaryData" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;">请同步更新OcBinaryData!</a></li><li style="box-sizing: border-box;">增加boot/quirks/ForceBooterSignature</li><li style="box-sizing: border-box;">增加UEFI/AppleInput</li><li style="box-sizing: border-box;">删除UEFI/ProtocolOverrides/AppleEvent</li></ul><h3 id="2021-03-17" style="box-sizing: border-box; margin-top: 18px !important; margin-bottom: 15px; font-family: inherit; font-weight: 600; line-height: 1.5; color: rgb(50, 50, 93); font-size: 22px;"><a href="https://blog.xjn819.com/post/opencore-guide.html#2021-03-17" class="headerlink" title="2021-03-17" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;"></a>2021-03-17</h3><p style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem; font-size: 1rem; font-weight: normal; line-height: 1.8; word-wrap: break-word;">适配OpenCore 0.6.7</p><ul style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem;"><li style="box-sizing: border-box;"><a target="_blank" rel="noopener" href="https://github.com/acidanthera/OcBinaryData" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;">请同步更新OcBinaryData!</a></li><li style="box-sizing: border-box;">增加UEFI/Audio/ResetTrafficClass</li><li style="box-sizing: border-box;">增加UEFI/Output/GopPassThrough</li><li style="box-sizing: border-box;">增加UEFI/Quirks/ActivateHpetSupport</li></ul><h3 id="2021-02-06" style="box-sizing: border-box; margin-top: 18px !important; margin-bottom: 15px; font-family: inherit; font-weight: 600; line-height: 1.5; color: rgb(50, 50, 93); font-size: 22px;"><a href="https://blog.xjn819.com/post/opencore-guide.html#2021-02-06" class="headerlink" title="2021-02-06" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;"></a>2021-02-06</h3><p style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem; font-size: 1rem; font-weight: normal; line-height: 1.8; word-wrap: break-word;">适配OpenCore 0.6.6</p><ul style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem;"><li style="box-sizing: border-box;"><a target="_blank" rel="noopener" href="https://github.com/acidanthera/OcBinaryData" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;">请同步更新OcBinaryData!</a></li><li style="box-sizing: border-box;">增加Kernel/quirks/SetApfsTrimTimeout</li><li style="box-sizing: border-box;">增加Misc/boot/LauncherOption</li><li style="box-sizing: border-box;">增加Misc/boot/LauncherPath</li><li style="box-sizing: border-box;">删除Misc/Security/BootProtect</li><li style="box-sizing: border-box;">增加Config/PlatformInfo/Generic/UseRawUuidEncoding</li><li style="box-sizing: border-box;">增加UEFI/Quirks/DisableSecurityPolicy</li><li style="box-sizing: border-box;">删除DeduplicateBootOrder</li></ul><h3 id="2021-01-18" style="box-sizing: border-box; margin-top: 18px !important; margin-bottom: 15px; font-family: inherit; font-weight: 600; line-height: 1.5; color: rgb(50, 50, 93); font-size: 22px;"><a href="https://blog.xjn819.com/post/opencore-guide.html#2021-01-18" class="headerlink" title="2021-01-18" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;"></a>2021-01-18</h3><ul style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem;"><li style="box-sizing: border-box;">增加Misc/Boot/PickerVariant<span class="Apple-converted-space">&nbsp;</span><a target="_blank" rel="noopener" href="https://github.com/acidanthera/OcBinaryData" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;">请同步更新OcBinaryData!</a></li><li style="box-sizing: border-box;">增加UEFI/Audio/SetupDelay</li><li style="box-sizing: border-box;">删除UEFI/Quirk/DeduplicateBootOrder</li><li style="box-sizing: border-box;">增加Config/PlatformInfo/Generic/MaxBIOSVersion</li></ul><h3 id="2020-12-12" style="box-sizing: border-box; margin-top: 18px !important; margin-bottom: 15px; font-family: inherit; font-weight: 600; line-height: 1.5; color: rgb(50, 50, 93); font-size: 22px;"><a href="https://blog.xjn819.com/post/opencore-guide.html#2020-12-12" class="headerlink" title="2020-12-12" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;"></a>2020-12-12</h3><p style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem; font-size: 1rem; font-weight: normal; line-height: 1.8; word-wrap: break-word;">适配OpenCore 0.6.4</p><ul style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem;"><li style="box-sizing: border-box;">增加booter/quirk/AllowRelocationBlock</li><li style="box-sizing: border-box;">增加booter/Patch</li><li style="box-sizing: border-box;">修改Misc/Boot/PickerAttributes</li><li style="box-sizing: border-box;">修改misc/Security/BootProtect</li><li style="box-sizing: border-box;">修改UEFI/Audio/PlayChime</li></ul><h3 id="2020-11-02" style="box-sizing: border-box; margin-top: 18px !important; margin-bottom: 15px; font-family: inherit; font-weight: 600; line-height: 1.5; color: rgb(50, 50, 93); font-size: 22px;"><a href="https://blog.xjn819.com/post/opencore-guide.html#2020-11-02" class="headerlink" title="2020-11-02" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;"></a>2020-11-02</h3><p style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem; font-size: 1rem; font-weight: normal; line-height: 1.8; word-wrap: break-word;">适配OpenCore 0.6.3</p><ul style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem;"><li style="box-sizing: border-box;">增加ForceResolution</li><li style="box-sizing: border-box;">增加ForceSecureBootScheme</li><li style="box-sizing: border-box;">增加CustomMemory</li></ul><h3 id="2020-10-14" style="box-sizing: border-box; margin-top: 18px !important; margin-bottom: 15px; font-family: inherit; font-weight: 600; line-height: 1.5; color: rgb(50, 50, 93); font-size: 22px;"><a href="https://blog.xjn819.com/post/opencore-guide.html#2020-10-14" class="headerlink" title="2020-10-14:" style="box-sizing: border-box; text-decoration: none; color: var(--themecolor); background-color: transparent; transition: color 0.25s ease; position: relative;"></a>2020-10-14:</h3><p style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem; font-size: 1rem; font-weight: normal; line-height: 1.8; word-wrap: break-word;">1.Opencore 0.6.2 正式版修改如下 variables:</p><ul style="box-sizing: border-box; margin-top: 0px; margin-bottom: 1rem;"><li style="box-sizing: border-box;">增加 ExtendBTFeatureFlags （章节2.4.6）</li><li style="box-sizing: border-box;">移除 DummyPowerManagement（章节2.4.6）</li><li style="box-sizing: border-box;">增加 LegacyCommpage（章节2.4.6）</li><li style="box-sizing: border-box;">增加 SystemMemoryStatus （章节2.7.2）</li><li style="box-sizing: border-box;">增加 ProcessorType（章节2.7.2）</li></ul></details>

------

## 0.0 BIOS设置

直接抄袭 @BAT 了

- **禁用:**

| 英文                                 | 中文                                                     |
| ------------------------------------ | -------------------------------------------------------- |
| Fast Boot                            | 快速启动                                                 |
| CFG Lock (MSR 0xE2 write protection) | CFG 锁 (MSR 0xE2 写入保护)                               |
| VT-d                                 | [VT-d](https://zhidao.baidu.com/question/495526512.html) |
| CSM                                  | 兼容性支持模块                                           |
| Intel SGX                            | Intel SGX                                                |

------

- **启用:**

| 英文                    | 中文                                                     |
| ----------------------- | -------------------------------------------------------- |
| VT-x                    | [VT-x](https://zhidao.baidu.com/question/495526512.html) |
| Above 4G decoding       | 大于 4G 地址空间解码                                     |
| Hyper Threading         | 处理器超线程                                             |
| Execute Disable Bit     | 执行禁止位                                               |
| EHCI/XHCI Hand-off      | 接手 EHCI/XHCI 控制                                      |
| OS type: Windows 8.1/10 | 操作系统类型: Windows 8.1/10                             |
| Legacy RTC Device       | 传统 RTC 设备                                            |

> 将操作系统类型设置为 `Windows 8.1/10` 是因为部分主板在 `Other` 模式下会将系统认作是 Windows 7 从而禁用 UEFI 的某些功能并开启 CSM, 200 系及以后的主板理论上不存在这个问题

------

## 1.0 整理OPENCORE目录

打开下载好的最新版 OC，把 Doc 文件夹下面的 `Sample.plist` 改名为 `config.plist`，并把此文件移动到 EFI 目录下面。
打开 `EFI--Kexts`，我们把常用的一些 kexts 先放进去，一般情况下你需要放如下 Kexts:

- [Lilu.kext](https://github.com/acidanthera/Lilu/releases) Acidanthera驱动全家桶的SDK
- [Applealc.kext](https://github.com/acidanthera/AppleALC/releases)  声卡驱动
- [VirtualSMC.kext](https://github.com/acidanthera/virtualsmc/releases)  传感器驱动依赖
- SMCProcessor.kext CPU核传感器
- SMCSuperIO.kext  IO传感器     
- [WhateverGreen.kext](https://github.com/acidanthera/whatevergreen/releases) 显卡驱动
- [IntelMausi.kext](https://github.com/acidanthera/IntelMausi/releases) Intel类千兆网卡驱动
- [Usbinjectall.kext](https://github.com/Sniki/OS-X-USB-Inject-All/releases) USB驱动 （你也可以定制自己的USB补丁）         

> 一些机型用了 `1820A,1560,1830` 等网卡，需要自己放对应驱动；有线螃蟹卡也自己放一下驱动；笔记本类需要更多传感器的，请自行补齐 `VirtualSMC` 的那些传感器补丁

------

打开`EFI--Drives`,里面的驱动介绍如下：

- AudioDxe.efi 开机UEFI界面若需要声音效果需要加载。
- CrScreenshotDxe.efi 开机UEFI的截图工具。
- HiiDatabase.efi 用于给 Ivy Bridge (3 代酷睿) 或更老代主板上支持 UEFI 字体渲染, UEFI Shell 中文字渲染异常时使用, 新主板不需要。
- NvmExpressDxe.efi 用于在 Haswell (4 代酷睿) 或更老的主板上支持 NVMe 硬盘, 新主板不需要。
- OpenCanopy.efi 加载第三方开机主题。
- OpenRuntime.efi 内存运用等必要的插件，必须加载。 
- OpenUsbKbDxe.efi 给使用模拟 UEFI 的老主板在 OpenCore 界面正常输入用的, 请勿在 Ivy Bridge (3 代酷睿)及以上的主板上使用。
- Ps2KeyboardDxe.efi PS2键盘所需插件。
- Ps2MouseDxe.efi PS2鼠标所需插件。
- UsbMouseDxe.efi 当MacOS被安装在虚拟机上所需要的鼠标插件。
- XhciDxe.efi 用于在 Sandy Bridge（2代）及之前或更老的主板上加载XHCI控制器。
- [HfsPlus.efi](https://blog.xjn819.com/tools/HfsPlus.efi.zip) 用于HFS格式文件系统，这是必须加载的。

------

## 2.0 Config.plist 修改

这章会把 config 的项目分开来，内容繁琐，为了让小白明白各个选项的用途。当然有能力的人可以直接看我最前面的几个链接来配置 `config.plist`。我这里强制要求你使用 `Propertree` 来编辑 `Config.plist`，其他的任何软件我都不建议使用。

------

### 2.1 Config–ACPI

ACPI包括了四个部分：`Add`, `Block`, `Patch`, `Quirks`。这里我们先把root下面的几条 `#WARNING` 删除，这几条没有实际意义。

------

### 2.1.1 Config–ACPI–Add

这部分主要填写我们使用的 SSDT 以及 DSDT 文件，如果没有请把 0-8 的 ssdt 全部删除。如果你有修改的 SSDT 或者 DSDT 文件，请先将文件放入 `EFI/OC/ACPI` 下。

因为我使用雷电卡，我需要添加两条关于雷电卡的 ssdt 文件：

```
Item 0
Comment    String       Thunderbolt3-DTGP //填一个你自己能辨别的名字，方便知道是啥
Enable     Boolean      YES                //表示加载此SSDT，反之NO则为不加载
Path       String       SSDT-DTGP.aml    //为你ssdt放在EFI/OC/ACPI下的文件名，必须一致
 
Item 1
Comment    String       Thunderbolt3
Enable     Boolean      YES
Path       String       SSDT-TB3.aml
```

------

### 2.1.2 Config–ACPI–Delete

这个目录下是禁用一些 SSDT/DSDT，没什么用，我把下面的 `item` 全都删了。

------

### 2.1.3 Config–ACPI–Patch 

这里我们需要填写一下热补丁。

- 10.15及以上系统，[一些资料](https://blog.daliansky.net/Common-problems-and-solutions-in-macOS-Catalina-10.15-installation.html)指出我们需要把EC控制器(EC0)改名为EC来确保能进入10.15系统

```
Comment:            EC0 to EC
Count:                0
Enabled:            YES
Find:                <4543305F>
Limit:                0
Mask:                <>
OemTable:            <>
Replace:            <45435F5F>
ReplaceMask:        <>
Skip:                0
TableLength:        0
TableSignature:        <>
```

> 一些主板的EC控制器名字可能会叫 H_EC 等，请自行提取 DSDT 并搜索 `PNP0C09`，来获取 EC 控制器的名字，这些内容会在第三章中写出。

------

- 华擎、华硕、微星主板可能会遇到采用新的 `AWAC` 时钟而无法进入系统，这同样需要添加 `hotpatch` 补丁来解决：

```
Comment:            RTC fix
Count:                0
Enabled:            YES
Find:                <A00A9353 54415301>
Limit:                0
Mask:                <>
OemTable:            <>
Replace:            <A00A910A FF0BFFFF>
ReplaceMask:        <>
Skip:                0
TableLength:        0
TableSignature:        <>
```

------

### 2.1.4 Config–ACPI–Quirks

此目录下有五项，选择与解释如下：

- FadtEnableReset:

   

  ```
  NO
  ```

  - 旧的主板需要对 FADT 进行标记来激活电脑的开机和关机功能，这里我们不许要启动它

- NormalizeHeaders:

   

  ```
  NO
  ```

  - 清理 ACPI 头，一些主板的 ACPI 表需要打开这个修复 10.13 系统的启动。

- RebaseRegions:

   

  ```
  YES
  ```

  - 尝试试探性地重新定位 ACPI 内存区域, **使用自定义 DSDT 则必须开启**

- ResetHwSig:

   

  ```
  NO
  ```

  - 存在重新启动后因无法维持硬件签名而导致从休眠中唤醒的问题的硬件需要开启

- ResetLogoStatus:

   

  ```
  NO
  ```

  - 无法在有 `BGRT` 表的系统上显示 OEM Windows 标志的硬件需要开启

- SyncTableIds:

   

  ```
  NO
  ```

  - 解决当用Opencore引导windows 7及更早的系统时，因缺少SLIC table而无法激活windows的问题。

------

## 2.2 Config–Booter

内存相关选项设置。

------

### 2.2.1 Config–Booter–MmioWhitelist

- 默认的第一项是为 Haswell 芯片提供的内存寻址修复，如果此类芯片碰到内存相关问题，请开启它(`enable`选择`yes`)。
- 默认第二项是开机卡 `PCI Configuration` 这里。ACPI、PCI device 同时释放到内存时发生 `0x1000` 内存地址被占用而卡在 `PCI Configration`，如果碰到此类问题，请开启它。

------

### 2.2.2 Config–Booter–Patch

- 该功能可以对Bootx64.efi进行修改。

------

### 2.2.3 Config–Booter–Quirks

此项与 `OpenRuntime.efi` 有关。在 `aptiomemoryfix` 停更后，此补丁已经更名为 `Openruntime`, 并将一些功能与 OC 合并、模块化。对于无法原生 `nvram` 的主板来说，这里的选项需要格外注意。当然我也会把像 300/400 系列、x299、C246、C422 这样支持原生 `nvram` 的选择方法一并写进去。

- **AllowRelocationBlock:** `NO`
  - 此功能用于10.7及更早的MacOS系统。当系统需要更低位置的内存时，该功能可以重新定位那些已经被非runtimeserivce所占据的内存。。
- **AvoidRuntimeDefrag:** `YES`
  - 大部分UEFI都会写入时间、电源管理等信息，这个所有黑苹果主板都应该选择 `YES`。
- **DevirtualiseMmio:** `YES`
  - 内存注入方式包括 `KASLR` 方式(分布式注射到各个内存地址中）以及连续性方式。在使用 `KASLR` 时，PCIe 加载到内存，可能会占据所有 `avaliable` 值而影响 OC 的内核以及内核缓存无法注入，导致启动失败。此项目前建议选择YES，并且在下一项 `ProtectUefiServices` 中也选择 `YES`。

> `KASLR` 是更加高效的内存注入方式，但不代表每台机器都能使用这种方案，这里我提供两种关于内存的设置：

> 1：`DevirtualiseMmio`选择`yes`, `ProtectUefiServices`选择`yes`, 并删除 [2.6.1](https://blog.xjn819.com/post/opencore-guide.html#2.6.1) 中 `boot-args` 里面的`slide=1`,以及删除 Drivers 文件夹下的 `Memoryallocations.efi`。即开启 `KASLR` 内存注入方式。 

> 2：`DevirtualiseMmio`选择`yes`, `ProtectUefiServices`选择`no`, 保留 [2.6.1](https://blog.xjn819.com/post/opencore-guide.html#2.6.1) 中 `boot-args` 里面的`slide=1`,以及保留 Drivers 文件夹下的 `Memoryallocations.efi`。即开启连续性内存注入方式。

- **DisableSingleUser:** `NO`
  - 这里关乎主机是否能开启单用户模式。什么是单用户模式，请看[此文章](https://support.apple.com/zh-cn/HT201573)。
- **DisableVariableWrite:** `NO`
  - 主板支持原生 `nvram`，请选择 `NO`。非原生NVRAM主板需要模拟 `nvram.plist` 进而写入 `variable` 值，因此我们要禁止此项来防止其他程序对 `nvram` 进行写入，我们这里选 `YES`
- **DiscardHibernateMap:** `NO`
  - 电脑从休眠(hibernation)中唤醒时,硬盘里的资料会恢复到内存中去，但这个时候 OC 的内核以及内核缓存等也会写入，这样可能导致冲突，这个选项是帮助我们解决这个问题的。而目前来看，除了原生 `NVRAM` 都无法进行休眠（注意睡眠 `sleep` 和休眠 `hibernation` 是两个概念），台式机的话就更不需要休眠功能了，这里我选择 `NO`。这里我们也不讨论如何休眠。
- **EnableSafeModeSlide:** `YES`
  - 安全模式下是否启用连续性的内存注入方式。我就选择 `YES`，与正常情况下保持一致。
- **EnableWriteUnprotector:** `YES`
  - 保证 `nvram` 能正常写入而不受到 `CR0` 寄存器的写入保护影响。
- **ForceBooterSignature:** `NO`
  - 休眠（hibernation）中唤醒使用OpenCore的SHA-1加密验证，我们不适用休眠功能就关闭。休眠不是睡眠！
- **ForceExitBootServices:** `NO`
  - 这个选项是让那些非常老旧的主板也能使用内存寻址，正常情况下选 `NO`。
- **ProtectMemoryRegions:** `NO`
  - 官方对此项目的解释与 `AvoidRuntimeDefrag` 类似，除非你明白这是什么，不然选择 `NO`，其实我也不明白。
- **ProtectSecureBoot:** `NO`
  - 保护安全启动，除非你开启安全启动，不然我们选择 `NO`。
- **ProtectUefiServices:** `NO`
  - 解决Z390系列主板卡开机卡++++的问题，这个功能从字面意思是与我提供的 `memoryallocation.efi`功能类似。
- **ProvideCustomSlide:** `YES`
  - 此选项执行固件的内存映射分析并检查所有的 `slide` 值(1 - 255)是否可用。由于 `boot.efi` 生成的这个值是利用 `rdrand` 指令随机生成的或者伪随机指令 `rdtsc` 随机生成的，因此当其选择了 一个冲突的 `slide` 值时有可能启动失败。由于这种潜在的冲突存在，此选项强制 macOS 在可用的值中使用一个伪随机值，这也确保了 `slide= `启动参数不会因为安全原因传递给操作系统。
    是否需要此选项由信息 OCABC (Only N/256 slide values are usable!) 是否存在于调试日 志中决定。如果存在此信息，则需要启用此 `Quriks` 选项。我选择 `YES`。如果你对 `KASLR`有一定的认知并会运用，请注意这个值。内容从 @套陆 摘抄。
- **ProvideMaxSlide:** `0`
  - 如果你没有启用 `KASLR` 的话，请填写 `1-255` 之间的数字以存放休眠文件写进内存所需要的内存高度，反之则填写 `0`。
- **RebuildAppleMemoryMap:** `NO`
  - 重新生成内存地图来匹配苹果系统。苹果的内核有很多缺陷，比如单张的内存地图不能超过 4K，一旦超过就可能无法开机；又比如一些硬件会直接把读写权限写进内存里，而苹果却不能给与写入权限。如果你遇到此类的问题，请尝试开启它。注意此项目与 `EnableWriteUnprotector` 存在冲突关系，确保开启这个的时候，另一个是关闭的。另外，此项又需要与 `SyncRuntimePermissions` 项搭配使用。一般情况下请选择 `NO`。
- **SetupVirtualMap:** `YES`
  - 是否建立虚拟内存并对物理内存进行映射。我们在开机时，OC 的程序需要一块连续性的内存进行存放内核等东西，而实际的物理内存一般都是分散的。因此，我们通过虚拟内存建立连续性内存供OC使用，并映射到分散的物理内存中。这里我们选择 `YES`。
- **SignalAppleOS:** `NO`
  - 通知同一台电脑上的设备 Mac 上的硬件选择，此项是给白苹果用的。

- SyncRuntimePermissions:

   

  ```
  YES
  ```

  - 修正硬件在注入内存时无法注入权限的问题。一般此类问题存在2018年后的主板。如果你因为此选项无法进入 windows，请开启它。

------

## 2.3 Config–DeviceProperties

此项是用来注入你的设备的，主要是显卡和声卡两部分。同样你也可以定制一些设备到你的 `关于本机--系统报告--PCI` 列表中，尽管没有多大的意义。

### 2.3.1 声卡 

这里首先我们需要确认自己的声卡驱动已经被加载，终端下输入：

```
kextstat | grep -E "AppleHDA|AppleALC|Lilu"

 
 
 
```

我们会得到被加载的驱动，请确保 `as.vit9696.Lilu`；`as.vit9696.AppleALC`；`com.apple.driver.AppleHDAController`；`com.apple.driver.AppleHDA` 已经被加载。

找自己声卡的地址，准备好在文章开头要求下载的 `gfxutil`，将 `gfxutil` 程序放在桌面，输入:

```
~/desktop/gfxutil -f HDEF //一般来说我们在使用 Applealc 后，板载声卡的部件名都叫 HDEF

 
 
 
```

我们输入后会得到声卡的PCI路径，比如我输出的就是：

```
00:1f.3 8086:a2f0 /PC00@0/HDEF@1F,3 = PciRoot(0x0)/Pci(0x1F,0x3)

 
 
 
```

这里我们找到的声卡 PCI 路径为 `PciRoot(0x0)/Pci(0x1f,0x3)`。我们把预先填写在那里的 `PciRoot(0x0)/Pci(0x1b,0x0)` 项替换成我们真正的声卡路径。

后面一段我们看到预先填写的声卡ID为 `<01000000>`，这里我们需要把它换成合适自己声卡的 ID，输入以下命令得到自己声卡的 CodecID。

```
ioreg -l|grep IOHDACodecVendorID

 
 
 
```

点击[此页面](https://github.com/headkaze/Hackintool/blob/master/Resources/Audio/Codecs.plist)搜索刚得到的CodecID就可查询到自己声卡的型号名称，以及可用的 `LayoutID`。

比如我的 CodecID 为 `283906408`，声卡型号 `ALCS1220A`，对应 1, 2, 3, 5, 7, 11, 13, 15, 16, 27, 28, 29, 34 的 `layout ID`。我们需要一个个测试过去，选定自己能用的。这里我们选择 7 这个 ID 进行测试，将 7 转化成 16 进制格式为 07，后面为了满足格式要求添加 6 个 0，则为 `07000000`，将这个值替换刚才预先填的` 01000000` 中；如果我们测试 ID 为 27，27 的 16 进制为 1b，补上 6 个 0 则为 `1b000000`。

```
PciRoot(0x0)/Pci(0x1f,0x3)
        device-id       data      <70a10000> //一般情况下这段是不需要填写的，除非你的声卡需要仿冒
        layout-id       data      <0b000000> //这个Layout id我瞎写的，你按实际情况写
```

如果你测试的ID都无效，请确保你的操作过程正确、并测试用万能声卡(VoodooHDA)补丁来替换 AppleALC 这个补丁。如果都不行，你可能需要自行[编译声卡补丁](https://blog.daliansky.net/Use-AppleALC-sound-card-to-drive-the-correct-posture-of-AppleHDA.html)。

------

### 2.3.2 核心显卡

打开 `PciRoot(0x0)/Pci(0x2,0x0)` 这项，此项为驱动核心显卡。驱动核心显卡我们要分情况讨论:

- 1.只有核心显卡的 DP 显示器用户 (HDMI设置请参照黑果小兵的博客）；
- 2.没有核心显卡的用户；
- 3.有核心显卡并用独显做主力的用户。

> 注意，这里我们只讨论 8代和9代CPU 的机器，其他CPU机型的请在论坛或者[黑果小兵博客](https://blog.daliansky.net/Intel-core-display-platformID-finishing.html)中搜索相关代码。

------

#### 2.3.2.1 只有核心显卡的DP显示器用户

8代和9代的核显ID为:`3E9b0007`，device ID为 `3e9b0000`，但是我们需要符合苹果的倒叙格式填入：

```
AAPL,ig-platform-id        data        <07009b3e>
device-id                  data        <9b3e0000>
framebuffer-unifiedmem     data        <00000080>      //核显显存相关
```

------

#### 2.3.2.2 没核心显卡的用户

带f的cpu (e.g. 9100f 9900kf), Xeon 等不带核心显卡的用户不需要管这项，直接把 `AAPL,ig-platform-id`选项卡删了。

------

#### 2.3.2.3 有核心显卡并用独显做主力的用户

这种情况我们一般把核心显卡作为加速用，而显示则用独立显卡。这样，我们填一个作为加速用的核显ID即可了，8代9代除外的 cpu 请搜索黑果小兵的博客：

```
AAPL,ig-platform-id        data        <0300983e>

 
 
 
```

> 注意，10代cpu虽然使用同样的UHD 630，但具体加速代码在iMac 20.1机型下不同，请自行查询

------

### 2.3.3 Delete

这里是禁用一些设备的，我们按默认就行了，不需要任何修改。

------

## 2.4 Config–Kernel

这里是内核相关选项。

------

### 2.4.1 Config–Kernel–Add

这里我们需要填写kexts的相关资料。值得注意的是 OC 的 kexts 填写必须注意顺序，比如 applealc 的依赖是 `lilu.kext`，那么 `lilu.kext` 必须填在第一个，`SMCProcessor.kext` 依赖于 `Virtualsmc.kext`。那 `Virtualsmc.kext` 必须放在 `SMCProcessor.kext` 之前。

这里默认情况下很多我们需要的补丁已经被加载里面了，但是 `enabled` 那块我们要手动改成 `yes` 去开启它，把一些不用的删了：

```
Item 0
      BundlePath       String         Lilu.kext            //kext的名字
      Comment          String                              //你自己填一个注释，可以不填
      Enabled          Boolean        YES                  //启动此补丁，反之则为关闭
      ExecutablePath   String         Contents/MacOS/Lilu  //通过右键kext显示包内容查找lilu运行文件的真正路径
      MaxKernel        String                              //此补丁支持的最大系统版本，填19为10.15，18位10.14；我们一般情况下留空
      MinKernel        String                              //此补丁支持的最小系统版本
      PlistPath        String         Contents/Info.plist  //kext的plist位置，可以右键kext显示包内容查找正确路径
       ............ ...........
       ............ ...........
 
Item 7
      BundlePath       String         USBPorts.kext
      Comment          String       
      Enabled          Boolean        YES
      ExecutablePath   String                              //一些没有执行文件的kext不需要填写
      MaxKernel        String
      MinKernel        String
      PlistPath        String         Contents/Info.plist
       ............ ...........
       ............ ...........
```

------

### 2.4.2 Config–Kernel–Block

禁用一些 kexts，这里好像没啥用，不用理会。

------

### 2.4.3 Config–Kernel–Emulate

此选项帮助 Ivy Bridge 和一些不受支持的CPU加载电源管理的，我们这里不做此方面讨论。所有选项按默认即可。

------

### 2.4.4 Config–Kernel–Force

特殊情况下我们需要强制加载某一些 `kext` 来达到某种目的，一般我们不理会此项。

------

### 2.4.5 Config–Kernel–Patch

这里是为内核打补丁用的，我会在进阶教程中详细写一下这一块。尤其是 rtc 相关的内容，我都会写进第三章的进阶教程。

------

### 2.4.6 Config–Kernel–Quirks

这里是内核相关的快捷选项，比较重要。

- **AppleCpuPmCfgLock:** `YES`
  - 四代之前的 CPU，如果未解锁 CFG(即MSR0xE2) 请选择 `YES`。
- **AppleXcpmCfgLock:** `YES`
  - 四代之后的CPU若未解锁 CFG(即MSR0xE2) 请选择 `YES`。
- **AppleXcpmExtraMsrs:** `NO`
  - 主要在没有原生电源管理的CPU上启用，一般是 `Haswell-E`, `Broadwell-E`, `Skylake-X` 这三种 CPU 需要填写 `YES`。除此之外的 CPU 选择 `NO`。
- **AppleXcpmForceBoost:** `NO`
  - 开启时将电脑的 cpu 频率锁定为最高频率。
- **CustomSMBIOSGuid:** `NO`
  - 戴尔笔记本专用项。
- **DisableIoMapper** `NO`
  - 禁用 vt-d。
- **DisableLinkeditJettison** `YES`
  - 提升 `lilu` 等插件在 MACOS 11 系统的表现，用来替代 `keepsyms=1`。
- **DisableRtcChecksum** `NO`
  - 越过两条 rtc 检查 (0x58及0x59)。RTC 我们会更多地使用 `RTCMemoryFixup.kext` 来防止它。
- **ExtendBTFeatureFlags** `NO`
  - 代替 `BT4LEContinuityFixup.kext` 来实现 `continuity`。
- **ExternalDiskIcons** `NO`
  - 修复苹果系统把内部硬盘识别为外置硬盘时（黄色图标的硬盘）开启。
- **ForceSecureBootScheme** `NO`
  - 只在MacOS安装在虚拟机并开启`SecurebootModel`时考虑开启。
- **IncreasePciBarSize** `NO`
  - 解决卡 PCI configuration，一般卡 pci configuration 都是因为自己错误的设置和硬件问题。
- **LapicKernelPanic** `NO`
  - 适用于HP笔记本的内核奔溃选项。
- **LegacyCommpage** `NO`
  - 老平台主板中使用 ssse3 需要开启来使用 macOS 10.4 - 10.6。
- **PanicNoKextDump** `YES`
  - 防止 `kext` 出错打报告而让我们看不到真正的 `panic` 原因，初始排错时最好打开。
- **PowerTimeoutKernelPanic** `YES`
  - 一些设备自身的电源管理无法让系统进入睡眠而超时，导致内核奔溃，如果有这个问题请选择 `YES`。
- **ProvideCurrentCpuInfo** `NO`
  - 给hyper-V虚拟化MacOS时提供cpu的信息，保证全核同步。
  - 
- **SetApfsTrimTimeout** `-1`
  - APFS文件系统根据空间是否`被使用`或者是`空的`来设计的，这种设计跟其他文件系统是不同的，一般被设计成`被使用`，`空的`或者`未映射`三种情况。这种不同可能带来在启动时系统需要更多的时间来做trim，甚至导致无法进入系统。这个选项是为了设计一个时间节点来终止trim进入系统。一般来说填入`-1`是不阻止这个trim过程，但如果你有这个问题，你可以设置一个时间，单位为微秒。
  - 因最近的系统更新，当trim过程超过10秒，系统开机时苹果会自动跳过trim，这样会导致一些品牌的ssd无法正常工作，出现系统崩溃，冻屏，死机等问题。解决的办法有两种，一种是将此选项设置一个超长的时间来保证trim结束，(e.g.4294967295)，带来的后果是开机非常慢，第二种方法是设置一个非常短的时间直接跳过trim过程（e.g.999）。关闭trim会带来大量的问题，所有的闪存不具备覆写的功能（除了傲腾），需要通过trim来删除日志中需要删除的空间，不然的话，硬盘的速度会直线下降。我们应该避免使用有这类问题的SSD。
  - 目前检查到的兼容性不够好的硬盘包括并不限于：
    - Samsung 950 Pro 
    - Samsung 960 Evo/Pro
    - Samsung 970 Evo/Pro
    - Samsung SM961
    - GIGABYTE 512 GB M.2 PCIe SS
    - ADATA Swordfish 2 TB M.2-2280
    - SK Hynix HFS001TD9TNG-L5B0B
    - SK Hynix P31
    - Samsung PM981 
    - Micron 2200V MTFDHBA512TCK
    - Asgard AN3+ (STAR1000P)
    - Intel 760p （一些批次）
    - Optane
    - 省略无数其他，列表中的有一些也许没问题，并不是一网打死。 

- **ThirdPartyDrives** `NO`
  - 开启 SATA 类 SSD 的 `trim` 功能，我没有 SATA 类的 ssd，我选择 `NO`。自行根据情况选择。
- **XhciPortLimit** `YES`
  - 解除 15 个 USB 端口限制。11.3系统不要开启，并自行定义usb端口。

------

### 2.4.7 Config–Kernel–Scheme

- **CustomKernel** `NO`
  - 当使用AMD/Atom等CPU时请开启。
- **FuzzyMatch** `NO`
  - 此选项是给 10.6 以及更早的系统使用，我们不做探讨。
- **KernelArch** `NO`
  - 此选项是给 10.7 以及更早的系统使用，不做探讨，直接填写默认的 `x86_64`。
- **KernelCache** `Auto`
  - 选择更加合适的内核缓存方式以提升启动速度。

------

## 2.5 Config–Misc

这里都是一些开机引导类的设置。

------

### 2.5.1 Config–Misc–BlessOverride

用于覆盖 Windows `bootmgfw.efi` 的位置以便识别 Windows 引导项, `OpenCore` 和 `Windows` 的引导文件在同一硬盘的同一个 ESP 分区下使用

```
▼ Misc                  <Dictionary>
|__ ▼ BlessOverride     <Array>
    |__ Item 0          <String>          \EFI\Microsoft\Boot\bootmgfw.efi
```

------

### 2.5.2 Config–Misc–Boot

- **ConsoleAttributes** `0`
  - 设置开机选择界面的颜色，默认直接填 0。使用方法为填入字体颜色和背景颜色的值的 16 进制之和。例如蓝色字 `(0x01)` + 红色背景 `(0x40)` = `0x41`。色彩选择如下：
- 字体颜色
  - 0x00 — 黑
  - 0x01 — 蓝
  - 0x02 — 绿
  - 0x03 — 青
  - 0x04 — 红
  - 0x05 — 艳红
  - 0x06 — 棕
  - 0x07 — 淡灰
  - 0x08 — 深灰
  - 0x09 — 淡蓝
  - 0x0A — 淡绿
  - 0x0B — 淡青
  - 0x0C — 淡红
  - 0x0D — 淡艳红
  - 0x0E — 黄
  - 0x0F — 白（这里是白色）
- 背景颜色
  - 0x00 — 黑
  - 0x10 — 蓝
  - 0x20 — 绿
  - 0x30 — 青
  - 0x40 — 红
  - 0x50 — 艳红
  - 0x60 — 棕
  - 0x70 — 淡灰
- **HibernateMode** `None`
  - 检测休眠模式。与系统内的休眠模式 (hibernatemode 25) 配合, 引导进系统会还原休眠前的状态, 建议关闭
  - `None`: 关闭休眠支持
  - `Auto`: 自动检测 RTC 和 NVRAM 模式
  - `RTC`: RTC 模式
- **HideAuxiliary** `NO`
  - 在tool下等具有Auxiliary并被开启的插件，补丁等是否需要被隐藏起来。
- **LauncherOption** `Disabled`
  - `Disabled`:对启动项不做任何事
  - `Full`:把OC的启动项永远置顶在uefi启动顺序中，填入此项后，你必须同时打开`RequestBootVarRouting`
  - `Short`:主要给`Insyde`cpu来使用并创建OC启动项。

- **LauncherPath** `Default`

  - `Default`: 自动加载默认的OpenCore.efi
  - `路径+xxx.efi`:给出指定路径来加载OC。比如我们把OpenCore.efi更名为qq.efi并放在\EFI\qq.efi，你就可以填写`\EFI\qq.efi`

- **PickerAttributes** `17`

  - 当你使用OC主题时，你可以通过计算以下数值之和来配合使用OC主题，建议使用数字`17`
  - `0x0001`: 是否加载自制的图标。如果是tool类的图标应该放在Resource/Image/xx.icon（与tool同名）；如果是自定义路径的启动硬盘，应放在同样位置并被命名为`路径.icns`。
  - `0x0002`: 在图标下显示渲染的文字指示。
  - `0x0004`: 使用默认的图标。
  - `0x0008`: 使用老式的图标。
  - `0x0010`: 在主题界面中允许使用鼠标。

  > 使用`17`这个值意味着是1+2+4+10

- **PickerAudioAssist** `NO`

  - 是否开启开机朗读文字功能，一般选择NO，如果你要开启，请同时阅读章节2.8.2和2.8.7的相关音频设置。

- **PickerMode** `Builtin`

  - `Builtin`: 不使用任何主题
  - `External`: 调用第三方主题
  - `Apple`: 给白果用的

- **PickerVariant** `Auto`

  - `Auto`: 自动选择，根据`DefaultBackgroundColour`来自动选择并具有时间控制的黑夜或白天的模式。
  - `Default`: 使用Resource/Images/GoldenGate/ 这个主题
  - `填路径`:使用自己的主题，主题文件夹该放在Resource/Images/下，比如Resource/Images/customised/xjn，则在这个选项中填customised/xjn

  > [官网推荐主题下载](https://github.com/acidanthera/OcBinaryData)
  > 请将下载好的Resources件放入ESP/EFI/OC下，同时，你需要将OpenCanopy.efi放入Drivers文件夹下并加载。

- **PollAppleHotKeys** `YES`

  - 是否开启一些热键功能，包括 ⌘+K，⌘+S

- **ShowPicker** `YES`

  - 是否显示开机启动盘选项。

- **TakeoffDelay** `0`

  - 开机热键延时，如果你按热键来不及按，你可以设置5000到10000之间的值让你有更多时间按热键（毫秒）。

- **Timeout** `5`

  - 倒计时进入指定硬盘，这里我们按需求填写，我填写5，代表5秒钟进入指定硬盘。

------

### 2.5.3 Config–Misc–Debug

是否开启debug模式，这里我们暂时不需要，全部按默认设置。

------

### 2.5.4 Config–Misc–Entries

这里是帮助我们添加一些你希望的引导路径，这个会在之后的进阶教程中讲，这里暂时略过不填写。

------

### 2.5.5 Config–Misc–Security

- **AllowNvramReset** `YES`
  - 是否在开机引导项中加入重置 `NVRAM` 功能的选项。
- **AllowSetDefault** `YES`
  - 选择 `yes` 后即可在开机选择系统页面中通过 Ctrl+Enter 键设置默认启动盘。
- **AllowToggleSip** `NO`
  - 在开机界面中增加一个关闭或开启sip的选项。
  - 
- **ApECID** `0`
  - 一般按默认的 0 填写，如果要开启安全启动的身份认证，请随便填写一串数字，比如手机号。
- **AuthRestart** `NO`
  - `Filevault` 相关项，选择 `NO`。
- **BlacklistAppleUpdate** `YES`
  - 如果使用MacOS 11，请开启它，因为在NVRAM中设置run-efi-updater并不能阻止苹果对固件的控制升级。

- **DmgLoading** `Any`
  - 如果你没有开启安全启动，请填写 `Any`；如果使用安全启动，请填写 `Signed`（注意大小写）。
- **EnablePassword** `NO`
  - 此选项正在开发。
- **ExposeSensitiveData** `2`
  - 模拟 `nvram`，填 3，如果你有原生 `nvram`，填写 2。
- **HaltLevel** `2147483648`
  - 按默认设置即可。
- **PasswordHash** `留空`
  - 按默认，如果开启了 `EnablePassword`，则填写密码的 `hash` 值。
- **PasswordSalt** `留空`
  - 按默认，如果开启了 `EnablePassword`，则填写密码的 `salt` 值。
- **ScanPolicy** `0`
  - 填0。我们也许会碰到开机的时候默认进入的系统永远是 WINDOWS，并无法更改，之后我们在进阶教程中讲述，如何让 MAC 盘排在第一个，让 WIN 排在后面。
- **SecureBootModel** `Disabled`
  - 是否开启安全启动模式，一般我们填写 `Disabled`（注意大小写）来关闭此功能。
- **Vault** `Optional`
  - 是否开启保险箱功能，我们选择 `Optional` 不开启它。

------

### 2.5.6 Config–Misc–Tools

用于运行 OC 调试工具, 例如验证 CFG 锁 (VerifyMsrE2)

- Arguments

  - 传递的参数

- Auxiliary:

   

  ```
  NO
  ```

  - `NO` 默认不隐藏

- Comment:

   

  ```
  随便填
  ```

  - 随便填

- Enabled

   

  ```
  YES/NO
  ```

  - 启用或禁用

- Flavour

   

  ```
  Auto
  ```

  - 当`PickerAttributes`设置成`0x0080`时适应主题需求

- Name

   

  ```
  名称（如 openshell ）
  ```

  - OpenCore 启动项中显示的名称

- Path

   

  ```
  文件名称（如 openshell.efi）
  ```

  - `Tools` 文件夹下的文件名

- RealPath

   

  ```
  NO
  ```

  - 一般不启用

- TextMode

   

  ```
  NO
  ```

  - 一般不启用

------

## 2.6 Config–NVRAM

------

### 2.6.1 Config–NVRAM–Add 

```
4D1EDE05-38C7-4A6A-9CC6-4BCCA8B38C14
    UIScale                     Data       <02> //这里填写01为普通的UI显示模式，02为开启HIDPI的UI显示模式，我选择02
    DefaultBackgroundColor      Data       <00000000> //默认开机背景色为黑色
 
7C436110-AB2A-4BBB-A880-FE41995C9F82
    boot-args                   String     Slide=1 darkwake=0 -v //slide=1 表示从第一组内存开始连续注入；darkwake=0 代表一键唤醒机器并偏好设置中节能选项的小憩功能。如果你要用小憩功能请填8； -v 是跑代码，在没装好稳定的黑果前我建议加上，方便定位错误，弄完后再删除 -v
    csr-active-config           Data       <e7030000> //关闭 SIP 保护
    nvda_drv                    Data       <31> //对 10.13 系统之前的N卡的相关设置，我们不做讨论。
    prev-lang:kbd               Data       <7a682d48616e733a323532> //语言设置相关，记得改成这个，这个是中文
    ForceDisplayRotationInEFI   Number     0   开机的UEFI界面是否需要调整，比如你是竖屏的，可以填0,90,180,270。请同时开启AppleEg2Info
    7C436110-AB2A-4BBB-A880-FE41995C9F82 //默认就行，如果需要使用 RTC 屏蔽选项，具体参考RTC综述
```

------

### 2.6.2 Config–NVRAM–Delete

NVRAM的数据不可被覆盖，必须先被删除再添加，我们这里按默认设置不必理会。

------

### 2.6.3 Config–NVRAM–LegacySchema

这里是模拟 `NVRAM` 的变量设置，大部分默认已经填好，我们只需添加两个变量即可。

打开 `7C436110-AB2A-4BBB-A880-FE41995C9F82` 这一栏，添加两个item如下：

```
item 11     String      efi-boot-device
item 12     String      efi-boot-device-data
```

------

### 2.6.4 Config–NVRAM–LegacyEnable

如果你的主板不支持原生 `NVRAM`，请一定要选择 `YES`，反之则选择 `NO`。

------

### 2.6.5 Config–NVRAM–WriteFlash

一般情况下我们需要选择 `YES` 来保证`启动磁盘`功能的正常使用，但开启后可能会在一段时间后导致 `CMOS` 被写满，主板无法经过自检。这样的问题请请参照[RTC综述](https://blog.xjn819.com/post/rtc-issues-related-to-oc.html)

------

### 2.6.6 Config–NVRAM–LegacyOverwrite

对模拟 `nvram` 用户来说，将 `nvram.plist` 写入硬件，我认为不管是原生 `nvram` 还是模拟 `nvram`，都选择 `NO`。

------

## 2.7 Config–PlatformInfo

这里我们填合适的机型。对于最近一代的主板来说，一般的原则，只有核显的机器我们选Macmini8,1；只有独显的机器我们选择iMac Pro 1,1;有核显和独显的我们选择iMac 19,1。笔记本请按照对应的cpu型号来选择。

------

### 2.7.1 Config–PlatformInfo–Automatic

是否自动补全系统信息。这里我选 `YES`，不重要的信息让它自动填。

------

### 2.7.2 Config–PlatformInfo–CustomMemory

自定义内存选项，请选择`NO`

------

### 2.7.3 Config–PlatformInfo–Generic

这里是我们需要填写的三码部分。

将 `OpenCore` 包下 `Utilities/macserial` 程序放到桌面，在终端下输入以下命令

```
~/desktop/macserial --model iMacPro1,1 //你也可以换成你想要的机型比如iMac 19.1

 
 
 
```

输入后你回获得一些序列号以及主板主板序列号，请自己选用一组，填写到 `MLB` 以及 `SystemSerialNumber` 后重启。

重启后，请再在终端下输入：

```
ioreg -d2 -c IOPlatformExpertDevice | awk -F\" '/IOPlatformUUID/{print $(NF-1)}'

 
 
 
```

得到你的主板 UUID，填入 `Generic` 的 `SystemUUID` （此操作可以帮助你的 win 不丢失激活）

- **AdviseFeatures** `YES`
  - 旧的主板不开启这项会让：
    - 当WINDOWS的EFI引导不在第一个分区时，将无法引导。
    - MacOS无法安装在APFS硬盘上。
- **MaxBIOSVersion** `0`
  - 一般情况填0，旧款的白苹果需要填写`9999.999.999.999.999`。
- **SystemMemoryStatus** `Auto`
  - 一些机型本身是可以升级内存，但在关于本机选项卡中不显示内存选项时需要开启，一般选择 `Auto`。
- **SpoofVendor** `YES`
  - 是否把主板名称更改为 ACDT，一般我们选择 `YES`。
- **ProcessorType** `0`
  - 为一些es，qs或者amd的cpu在关于本机中显示核心数。
- **UpdateDataHub** `YES`
  - 更新DataHub。

- **UpdateNVRAM** `YES`
  - 更新NVRAM。
- **UpdateSMBIOS** `YES`
  - 更新 BIOS
- **UpdateSMBIOSMode** `Create`
  - 用新分配的 `EfiReservedMemoryType` 替换原有的表, 戴尔笔记本需要使用 `Custom` 并开启 `CustomSMBIOSGuid`
- **UseRawUuidEncoding** `NO`
  - 一般来说我们都选`NO`
  - 除非你的UUID，比如：`AABBCCDD-EEFF-GGHH-IIJJ-KKLLMMNNOOPP`。解码后即是`AA BB CC DD EE FF GG HH II JJ KK LL MM NN OO PP`，但在实际系统中显示`DD CC BB AA FF EE HH GG II JJ KK LL MM NN OO PP`。你需要开启这个选项。

------

## 2.8 Config—-UEFI

------

### 2.8.1 Config–UEFI–APFS

- **EnableJumpstart** `YES`
  - 从 APFS 容器中加载内置 APFS 驱动，建议开启 `YES`。此选项仍然依据你的`Scanpolicy`来做出决定，请确保在`Scanpolicy`中放开 APFS 格式。
- **GlobalConnect** `NO`
  - 一些主板需要选择 yes 才能完全加载 APFS，比如 HP笔记本。
- **HideVerbose** `YES`
  - 是否隐藏啰嗦模式，一般我们需要看日志的时候才开启，所以我们选择隐藏，选择 `YES`。
- **JumpstartHotPlug** `YES`
  - 是否加载 APFS 格式的热插设备.
- **MinDate** `0`
  - 加载最低发行的 APFS 格式。一些旧的 APFS 可能会危害电脑，我们填 `0`。如果你想加载旧的发行日期的 APFS 格式硬盘，请填 `-1`。
- **MinVersion** `0`
  - 加载最低版本的 APFS 格式。填 `0` 代表从 `HIGH SIERRA` 开始加载。填` -1` 代表所有版本，建议填 `0`。

------

### 2.8.2 Config–UEFI–AppleInput

- **AppleEvent** `Auto`

  - 在UEFI界面中使用APPLE自带的键鼠控制还是用OC制作的。
    - 填写`Builtin`：使用OpenCore的控制
    - 填写`OEM`：使用Apple自带的控制
    - 填写`Auto`：自动选择

- **CustomDelays** `NO`

  - 在UEFI界面中控制键盘连击的延迟。当

    ```
    AppleEvent
    ```

    =OEM 时此选项无效。

    - `NO`：使用Apple默认的500ms首次延迟和50ms的随后延迟。
    - `YES`：根据`KeyInitialDelay` `KeySubsequentDelay`来设置延迟。

- **KeyInitialDelay** `50`

  - 设置UEFI界面第一次延迟时间，50是500ms，此选项必须在`CustomDelays`=True时生效。

- **KeySubsequentDelay** `5`

  - 设置UEFI界面键与键之间的延迟时间，5是50ms，此选项必须在`CustomDelays`=True时生效。

- **GraphicsInputMirroring** `YES`

  - `NO`: 使用Apple的键盘控制，这可能导致在一些环境下无法使用键盘输入(e.g. Windows BitLocker)。
  - `YES`:可以让OpenCore在引导一些系统的UEFI模式下时仍然可以使用键盘输入。

- **PointerSpeedDiv** `1`

  - 设置UEFI界面中，光标的跟踪速度版本，一般填1。

- **PointerSpeedMul** `1`

  - 设置UEFI界面中，光标的灵敏度版本，一般填1。

------

### 2.8.3 Config–UEFI–Audio

此项的内容是帮助你在开机阶段驱动板载音频，此项对DP等数字音频无效。

- **AudioCodec** `0`
  - 填写音频声卡in节点。可以用 `PinConfigurator` 提取。
- **AudioDevice** `0`
  - 填写你声卡的路径。这里我们填写[章节2.3.1](https://blog.xjn819.com/post/opencore-guide.html#2.3.1)中寻找到的声卡路径。这里我填了 `PciRoot(0x0)/Pci(0x1f,0x3)`，请按你自己的实际情况填写。
- **AudioOut** `0`
  - 音频声卡out节点。可以用 `PinConfigurator` 提取。
- **AudioSupport** `NO`
  - 是否开启黑苹果的提示音支持。
- **MinimumVolume** `20`
  - 声音音量，范围在 `0-100` 之间。
- **PlayChime** `Auto`
  - 是否开启开机提示音；如果需要开启请填入`Enabled`。
- **ResetTrafficClass** `No`
  - 在不使用`AppleALC.kext`时驱动声卡，一些芯片组上的声卡并不被设置为TC0，比如[ICH09](https://www.intel.cn/content/www/cn/zh/io/io-controller-hub-9-datasheet.html)。当我们使用AppleALC时，默认被设置为了alctsel。
- **SetupDelay** `0`
  - 一些`codecs`要求特殊的延迟才能正常使用。一般填0，而如需填写以0.5为单位增加。
- **VolumeAmplifier** `0`
  - 非必要情况下填写0。

> 开启UEFI加载阶段的音频你必须下载[Audio文件夹](https://github.com/acidanthera/OcBinaryData/tree/master/Resources),并把 Audio 文件夹放到 `ESP/EFI/OC/Resources` 下。另外你必须注意 `AppleAudio` 选项。

------

### 2.8.4 Config–UEFI–ConnectDrivers

是否加载补丁，我们选择 `YES`。

------

### 2.8.5 Config–UEFI–Drivers

```
Drivers
item0                      String
0 .................... MemoryAllocation.efi
1 .................... OpenRuntime.efi
2 .................... HFSPlus.efi
3 .................... OpenCanopy.efi
```

### 2.8.6 Config–UEFI–Input

此选项是原生 Apple 开机热键的选项，需要配合我们之前设置的 `PollAppleHotKeys = yes` 一起用。下面的设置完全按照默认情况就行了。

> 如果你是华硕的z87或者z97，你需要打开PointerSupport这个选项。

------

### 2.8.7 Config–UEFI–Output

- **ClearScreenOnModeSwitch** `NO`
  - 消除开机时从图形模式转换到文本时出现残影的问题，如果没有这个问题我们选择 `NO`。
- **ConsoleMode** `MAX`
  - 主机的输出方式，一般情况下填 `MAX`，或者留空。
- **DirectGopRendering** `NO`
  - 是否使用内置显卡直接渲染开机画面。
- **ForceResolution** `NO`
  - Intel `Ironlake/Arrandale` 及之前的核心显卡需要开启此功能来自定义分辨率。
- **GopPassThrough** `Disabled`
  - 在UGA环境中调用显卡GOP。若要开启它，你必须同时开启`ProvideConsoleGop`。

- **IgnoreTextInGraphics** `NO`
  - 修复在不使用 `-v` 跑马模式时候，开机日志导致的苹果 LOGO 显示不正确的问题。
- **ProvideConsoleGop** `YES`
  - 调用显卡 GOP。
- **ReconnectOnResChange** `NO`
  - 一些固件在 GOP 分辨率改变后会重新连接显示器才能输出，一般情况下选择 `NO`。
- **ReplaceTabWithSpace** `NO`
  - 一些固件在 `UEFI Shell` 下 Tab 功能键不生效，开启这个会用空格键代替。
- **Resolution** `留空`
  - 开机 UEFI 阶段的分辨率。比如我的显示器是 4K、16：9 的，就填写 `3840x2160`。根据情况填写或者不填。
- **SanitiseClearScreen** `YES`
  - 修复 4K 及以上显示器的输出问题。
- **TextRenderer** `BuiltinGraphics`
  - OC 开机代码字体渲染方式
- **UgaPassThrough** `NO`
  - 通过 uga 来代替那些无法使用 gop 的主板，一般带 uefi 的主板以及显卡请选择 `NO`。

------

### 2.8.8 Config–UEFI–ProtocolOverrides

- **AppleAudio** `NO`
  - 如果你想要开启如同白苹果一样的开机音效，请开启它，并且还需要配合 `UEFI--Audio` 的正确设置。
- **AppleBootPolicy** `NO`
  - 虚拟机的 Mac 需要用的。
- **AppleDebugLog** `NO`
  - 重新安装苹果错误日志界面。
- **AppleEg2Info** `NO`
  - 配合`ForceDisplayRotationInEFI`调整开机时画面的显示角度，当你要用竖屏的时候不仅要在nvram中设置`ForceDisplayRotationInEFI`的角度，这个也要开启。

- **AppleFramebufferInfo** `NO`
  - 为虚拟机使用，不是虚拟机选择 `NO`。
- **AppleImageConversion** `NO`
  - 重建 Apple 图标。
- **AppleImg4Verification** `NO`
  - 当开启安全启动时必须开启它。
- **AppleKeyMap** `NO`
  - 重建苹果功能键。
- **AppleRtcRam** `NO`
  - 重装 `AppleRtc` 协议。
- **AppleSecureBoot** `NO`
  - 苹果安全启动协议。
- **AppleSmcIo** `NO`
  - 代替之前的 `VirtualSMC.efi`，在使用`vault`功能时需要开启。
- **AppleUserInterfaceTheme** `NO`
  - 重新安装 `Apple User Interface Theme` 协议。
- **DataHub** `NO`
  - 重建 `Datahub`。
- **DeviceProperties** `NO`
  - 虚拟机或者老款的电脑需要选择 `YES` 才能注入 `Device Property`，我们选NO。如果你发现你注入 `Device Property` 无效，请选择 `YES`。
- **FirmwareVolume** `NO`
  - Vault/虚拟机/老款 Mac 需要开启才能相关项。
- **HashServices** `NO`
  - Vault 相关项。
- **OSInfo** `NO`
  - 通知主板以及一些程序关于 Mac 引导的信息，一般情况选择 `NO`。
- **UnicodeCollation** `NO`
  - 旧的主板需要，我们选 `NO`。

------

### 2.8.9 Config–UEFI–Quirks

- **ActivateHpetSupport** `NO`
  - 老主板比如ICH6芯片组不具备相关的HPET设置，老的主板你可能需要开启它。
- **EnableVectorAcceleration** `YES`
  - 在CPU支持avx512或者avx的情况下，在UEFI界面中开启avx加速。
  - 
- **DisableSecurityPolicy** `NO`
  - 关闭主板的UEFI上的Secure Boot。请`不要`在BIOS中开启`Secure Boot`并同时开启这个！
- **ExitBootServicesDelay** `0`
  - 旧主板需要给予主板退出时间（单位为微秒），较新的主板直接填 `0`。旧的主板比如 Z87pro，填 `3000000-5000000`。
- **ForgeUefiSupport** `NO`
  - 旧的NVIDIA显卡使用UEFI 2.0的gop，但在一些老的MAC中只支持UEFI 1.X。这个开关帮助旧的MAC使用NVDIA2.0的GOP。
- **IgnoreInvalidFlexRatio** `NO`
  - 如果你没有在 BIOS 中解锁 `MSR0x194`，一定要选YES。
- **ReleaseUsbOwnership** `NO`
  - 大部分的主板都有自动释放 USB 所有权的功能——BIOS/XHCI EHCI hand-off，我们选 `NO`。如果你开机键盘鼠标卡死了，或者 USB 失灵，试试选 `YES`。
- **ReloadOptionRoms** `NO`
  - 配合`ForgeUefiSupport`使用。
- **RequestBootVarRouting** `YES`
  - 增加 `启动磁盘` 的可靠性。
- **TscSyncTimeout** `0`
  - 帮助一些 X99、X299 的主板开启全核同步功能。此选项旨在代替 `TSCAdjustReset.kext` 等类似补丁，推荐的值是 `500000`。但是此选项并不能在睡眠唤醒后生效，所以请填写默认值 `0`，并使用 `TSCAdjustReset.kext` 来做全核同步。
- **UnblockFsConnect** `NO`
  - 惠普笔记本可能会让 OC 无法扫描到启动项，一般选择NO，如果你是惠普笔记本，请选择YES。

------

### 2.8.10 Config—-UEFI—-ReservedMemory Properties

此项为保留内存所用。一些硬件会把硬件 EFI 写进内存过程中占据必要的 UEFI 运行空间，所以我们可以通过此项来预留内存来保证 UEFI 的运行。填写方式可以参考[小兵的文章](https://blog.daliansky.net/Slide-value-acquisition-and-calculation.html)。来寻找指定内存的起始位置，以 4K 为一个节点。一般情况下，此项我们并不需要理会。

------

## 3.0 OpenCore 完善

### 3.1 模拟NVRAM 

对 OC 而言，`NVRAM` 是非常核心的一环，不管是原生还是模拟的。如果你是原生nvram的主板，请不必理会这章节。

这章节的主要内容为非原生 NVRAM 模拟生成 `nvram.plist`。

- 首先打开我们之前下载好的 OpenCore，进入目录下的 `Utilities/LogoutHook` 文件夹，你会看到 `LogoutHook.command` 文件。
- 打开 Terminal（终端）并输入 `cd ~` 返回到用户根目录，输入 `mv` 和一个空格，然后鼠标拖动 `LogoutHook.command` 文件到 Terminal（终端），再在终端输入 `~/.LogoutHook.command`

```
例如（不要直接复制这条命令行）
 mv /Users/xjn/Downloads/OpenCore-0.6.2-RELEASE/Utilities/LogoutHook/LogoutHook.command ~/.LogoutHook.command
```

- 最后在 Terminal（终端）中，输入以下命令按回车：

```
sudo defaults write com.apple.loginwindow LogoutHook /Users/$USER/.LogoutHook.command

 
 
 
```

- 终端会提示要求你输入密码（密码打进去不会显示）。
- 重启，你会在 `ESP/EFI/` 下看到 `nvram.plist`，代表已经成功模拟了。

------

### 3.2 建立自己的开机选择系统目录

<details style="box-sizing: border-box;"><summary style="box-sizing: border-box; display: list-item; cursor: pointer;"><font color="red" style="box-sizing: border-box;">因此部分需求太小众且繁琐，我折叠起来了，点击展开</font></summary></details>

------

### 3.3 提取DSDT

尽管提取原始DSDT的方法非常多，我认为 `CLOVER` 的提取方法是最方便并且靠谱的。我们需要一个空的U盘或者空的ESP分区，我的教程是非常偏向小白的，所以这里提取我也会用到windows，以及Diskgenius这个软件，做最简单的示范。

- 进入Windows，插入U盘，打开[DiskGenius](https://www.diskgenius.cn/download.php)，选中我们的U盘，并选择顶部菜单栏的快速分区
  - 分区表类型：`GUID`
  - 不要创建新的 `ESP` 分区
  - 不要创建新的 `MSR` 分区
  - 分区格式为 `FAT32`
- 格式化完成后，放入我从黑果小兵镜像包提取出来的[EFI](https://blog.xjn819.com/tools/EFI.zip)放进去。这是一个 clover 引导，但并不能引导你的系统，只能提取 DSDT。
- 插上U盘，重启，通过U盘引导，看到Clover界面，我们按F4，这样原始的DSDT文件就收集好了。
- 重新通过OC引导进入系统，我们打开U盘，EFI/Clover/ACPI/Orgin下，有我们的原始ACPI内容，我们只需要DSDT.aml这个就行了，保存到安全的地方。

------

### 3.4 加载原生电源管理

提取 DSDT 后使用 `MaciASL` 打开，搜索你 CPU 的名字。一般情况下，CPU 的名字可能是: `PR.CPU0`,`PR.P000`,`PR.PR00`,`SB.CPU0`,`SB.P000`,`SB.PR00`, `SCK0.C000`, `SCK0.CPU0`。请依次搜索直到找到自己的CPU名字，比如我的就是`SCK0.C000`

```
Processor (C000, 0x00, 0x00001810, 0x06)
                {
                    Name (_HID, "ACPI0007" /* Processor Device */)  // _HID: Hardware ID
                    Name (_UID, "SCK0-C000")  // _UID: Unique ID
                    Method (_PXM, 0, NotSerialized)  // _PXM: Device Proximity
                    {
                        If ((CLOD == 0x00))
                        {
                            Return (0x00)
                        }
                        Else
                        {
                            Local0 = DerefOf (APT0 [0x00])
                            Local1 = CNBS /* \CNBS */
                            Local1 -= 0x01
                            Local0 >>= Local1
                            Local0 &= 0x01
                            Local1 = 0x00
                            Local1 *= 0x02
                            If ((Local0 == 0x01))
                            {
                                Local1 += 0x01
                            }
 
                            Return (Local1)
                        }
                    }
```

打开宪武大大的[OC Little](https://github.com/daliansky/OC-little)，到 `05-注入设备/05-1-注入x86/` 目录下，我们看到宪武大大已经把大部分不同名字的CPU的 dsl 文件都做好了。我的 CPU 名字叫 `SCK0.C000`，打开 `SSDT-PLUG-_SCK0.C000.dsl`，左上角另存为（save as), 其中文件格式(file format)必须选择 `ACPI Machine Language Binary`，文件名字随便写吧，我就叫 `plug-xcpm.aml`，记住后缀为 `.aml`。

将 `plug-xcpm.aml` 放入 `EFI/OC/ACPI` 下，并在 `config.plist` 中添加加载此 aml 文件:

```
ACPI
  Add
    Item 0
      Comment    String       plug-xcpm
      Enable     Boolean      YES
      Path       String       plug-xcpm.aml
```

加载后，重启，并清理一次 `nvram`，我们看到偏好设置–节能中，原生电源管理已经被加载了。

------

#### 3.4.1 节能五项

节能五项是白果台式机中，`系统偏好设置`—`节能` 中的五个选项。在加载原生电源管理后，一般有4项节能出现，而第五项“断电后重启”这项还需要加载 `PPMC` 以及 `LPCB` 下的 `PMCR` 才能出现。虽然没啥鸟用，但对于强迫者而言，少一个一定很难受吧。如果你是笔记本，不需要看这章，白果笔记本本身没有。如果你没有机械硬盘，也不会出现 `Put hard disks to sleep when possible`。

直接下载[SSDT-PM.aml](https://blog.xjn819.com/tools/SSDT-PM.zip)载入即可。

------

### 3.5 解锁 macOS 的系统目录

bugprogrammer给出了一个一劳永逸的解决方案：

[解锁macOS10.15的系统分区](http://www.bugprogrammer.me/2019/07/13/unlockSystem.html)

11系统的解锁略麻烦：[解锁MacOS11的系统区](https://www.bugprogrammer.me/2020/07/09/about-BigSur.html#删除快照，重获权限)

------

### 3.6 关于EC控制器

EC控制器是电脑自带的一个叫 `embedded controller` 的部件。在 10.15 的系统环境中，笔记本电脑必须重命名原来的 EC，而一些台式机主板则需要禁用。下面我会分开来讲解如何禁用 EC、如何加载 USB 电源管理支持。

------

#### 3.6.1 禁用EC控制器

[之前的章节](https://blog.xjn819.com/post/opencore-guide.html#2.1.3)中提供了重命名这种方式去讲 EC0 更名为 EC，其实这种方法是只适合笔记本的，台式机最好还是禁用 EC。

打开之前提取出来的 DSDT.aml，搜索 `PNP0C09`，这里我搜到我的EC真实名字叫做 `H_EC`，你的可能叫 `EC0` 或者别的什么奇怪的名字。

这里我可以看到我的 `H_EC` 已经是屏蔽掉的，怎么判定，你看下面有一个 `Return (Zero)`，意味着这个部件是不生效的，即禁用。这样的情况我们不需要做任何 SSDT 去禁用这个真的 EC。

```
    Scope (_SB.PCI0.LPCB)
    {
        Device (H_EC)
        {
            Name (_HID, EisaId ("PNP0C09") /* Embedded Controller Device */)  // _HID: Hardware ID
            Name (_UID, One)  // _UID: Unique ID
            Method (_STA, 0, NotSerialized)  // _STA: Status
            {
                ^^^GFX0.CLID = 0x03
                Return (Zero)
            }
```

那么什么样的情况是需要我们去屏蔽的呢？我发现基本上华硕的台式机主板都会启用这个EC控制器，下面代码是华硕主板的EC部件，搜索 `PNP0C09`，我们看到这种情况下，这个叫 EC0 的 `EC` 控制器是开启的，注意他没有 `return (Zero)` 这个语句，我们需要通过 SSDT 去屏蔽它。

```
        Device (EC0)
        {
            Name (_HID, EisaId ("PNP0C09") /* Embedded Controller Device */)  // _HID: Hardware ID
            Name (_CRS, ResourceTemplate ()  // _CRS: Current Resource Settings
            {
                IO (Decode16,
                    0x0062,             // Range Minimum
                    0x0062,             // Range Maximum
                    0x00,               // Alignment
                    0x01,               // Length
                    )
                IO (Decode16,
                    0x0066,             // Range Minimum
                    0x0066,             // Range Maximum
                    0x00,               // Alignment
                    0x01,               // Length
                    )
            })
```

这里我提供了一个禁用 EC 的补丁，请直接下载，打开后左上角另存为（save as), 其中文件格式(file format)必须选择 `ACPI Machine Language Binary`，文件名字随便写吧，我就叫 `ssdt-no-EC.aml`，记住后缀为 `.aml`。将 `ssdt-no-EC.aml` 放入 `EFI/OC/ACPI` 目录下，并在 `config.plist` 中加载此 aml 文件。

直接下载[SSDT-PM.aml](https://blog.xjn819.com/tools/SSDT-no-EC.dsl.zip)载入即可。

如果你的 EC 名字叫 H_EC 或者别的什么的，你打开这个 `.dsl` 文件，替换代码中所有的 EC0 为 H_EC。

```
{
    External (_SB.PCI0.LPCB, DeviceObj)
    External (_SB_.PCI0.LPCB.H_EC, DeviceObj)
 
    Scope (\_SB.PCI0.LPCB.H_EC)
    {
        Method (_STA, 0, NotSerialized)  // _STA: Status
        {
            If (_OSI ("Darwin"))
            {
                Return (0)
            }
            Else
            {
                Return (0x0F)
            }
        }
    }
 }
```

> 当你的电脑没有EC后，你仍然需要仿冒EC来完成全部操作。

------

#### 3.6.2 重命名EC控制器

笔记本不能禁用 EC，禁用 EC 后会直接导致笔记本没有电池。那么我们怎么去重命名 EC 呢？按照上面提到的方法，找到你 EC 的真实名字，在[之前的章节](https://blog.xjn819.com/post/opencore-guide.html#2.1.3)中我提供了假如你的笔记本的 EC 叫做 `EC0` 时候的重命名办法，那如果你的 E C叫别的乱七八糟的名字呢？

EC 名，比如你的 EC 叫做 `H_EC`，我们打开在线的[HEX转换器](https://tool.lu/hexstr/)，输入 `H_EC`，并点击下面的16进制转换，就可以看到转换出来的值是 `485F4543`，把这个值替换到 `Find` 这个选项卡中就行了。你也会注意到，EC 的 hex-16 进制为 `45435F5F`，刚好是 `Replace` 的值。这就是一个非常简单实用的 OC 重命名。切记！OC 万不得已不要用重命名！

```
Comment:                H_EC to EC
Count:                    0
Enabled:                YES
Find:                    <485F4543>
Limit:                    0
Mask:                    <>
OemTable:                <>
Replace:                <45435F5F>
ReplaceMask:            <>
Skip:                    0
TableLength:            0
TableSignature:            <>
```

------

#### 3.6.3 仿冒EC及USBX供电

禁用EC后你需要创建仿冒EC来进入系统，同时开启USB的快速供电技术（需设备支持）。你可以比较下面两张图，第二张是功能正确开启的。
![Screen Shot 2020-10-31 at 3.40.07 PM.png](data:image/svg+xml;base64,PCEtLUFyZ29uTG9hZGluZy0tPgo8c3ZnIHdpZHRoPSIxIiBoZWlnaHQ9IjEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgc3Ryb2tlPSIjZmZmZmZmMDAiPjxnPjwvZz4KPC9zdmc+)

这部分内容是仿冒 EC，注意不是每一个DSDT的路径都在 `SB.PCI0.LPCB`，请搜索 `0x001F0000` 来确定实际位置和名称。比如我的主板是在 `SB.PC00.LPC0`。

```
    Scope (\_SB.PCI0.LPCB)
    {
        Device (EC)
        {
            Name (_HID, "ACID0001")  // _HID: Hardware ID
            Method (_STA, 0, NotSerialized)  // _STA: Status
            {
                If (_OSI ("Darwin"))
                {
                    Return (0x0F)
                }
                Else
                {
                    Return (Zero)
                }
            }
        }
    }
```

![Screenshot-2020-02-05-at-10.47.54-AM.png](data:image/svg+xml;base64,PCEtLUFyZ29uTG9hZGluZy0tPgo8c3ZnIHdpZHRoPSIxIiBoZWlnaHQ9IjEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgc3Ryb2tlPSIjZmZmZmZmMDAiPjxnPjwvZz4KPC9zdmc+)

------

### 3.7 睡眠即醒的相关问题

睡眠即醒很大程度上跟 USB 的定制相关，一般一个好的 USB 定制就能解决睡眠即醒的问题。当然还有很多无法解决的问题，比如蓝牙不能在 HUB 下进行内建，等等。甚至有些时候我们都不知道为什么黑果会睡不着，那有没有一个办法让黑果强制睡眠呢？答案是有的。经过我的摸索，有几种方法能达到强制睡眠的效果，只是方法不同而已，但主要围绕的还是 `0d/6d` 的数值来做一些工作。这些方法涉及了很多 OC 领域的一些小技巧，我也顺便展示给大家。

> `0d/6d` 补丁是阻止一些部件参与唤醒工作，这其中包括了xhc部件，意味着你无法使用鼠标键盘唤醒，只能用电源键唤醒。但若你有一组除了xhc之外的usb控制器，那把键盘鼠标插在那两个控制器上，可以在使用强制睡眠的情况下用键盘鼠标唤醒电脑。

------

#### 3.7.1 分辨0D/06

主板一般有5个部件是直接参与唤醒工作的，这五个部件分别是 XHC（USB控制器）、CNVW（CNVI网卡，如果你的主板自带或者预留了口的话）、GLAN（有线网卡）、XDCI（USB相关）、HDEF（音频）。旧的一些主板可能会有不同的命名，比如 XHC 有叫 EH01，HDEF 叫做 HDAS 等，这里不做讨论。而这些设备往往会直接影响睡眠，比如你输入：

```
log show --last 1d | grep "Wake reason"

 
 
 
```

我们会看到类似的输出结果

```
2020-10-31 03:35:45.196371+0800 0x74       Default     0x0                  0      0    kernel: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: XDCI CNVW
2020-10-31 03:35:45.196373+0800 0x74       Default     0x0                  0      0    kernel: (AppleACPIPlatform) AppleACPIPlatformPower Wake reason: XDCI CNVW
```

那么即 是`XDCI` `CNVW` 导致了睡眠出现了问题。于是，我们用几种方法去屏蔽或者说修改这些部件，来达到电脑正常睡眠的效果。

我们打开之前提取的SSDT，随便搜索五大部件中的一个，比如说 XDCI：
![截屏2019-11-07下午11.06.02.png](data:image/svg+xml;base64,PCEtLUFyZ29uTG9hZGluZy0tPgo8c3ZnIHdpZHRoPSIxIiBoZWlnaHQ9IjEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgc3Ryb2tlPSIjZmZmZmZmMDAiPjxnPjwvZz4KPC9zdmc+)

主要是看上图中 `XDCI` 下的 `_PRW` 属性值，可以直接看到 Return 的值为 `GPRW (0x6D, 0x04)`。其中 `6D` 这个数值看主板而定，有些主板叫做 `0D`，而后面 `04` 这个值的含义为 S4 级别的电源管理，即休眠甚至关机情况下的唤醒；有些后面的数值是 `03`，代表着 S3 级电源管理。这个我打一个大家比较熟悉的例子， `GLAN` 这个网卡部件的 `PRW` 值也是 `0x04`，为什么要是 `04` 呢？因为这样我们可以使用远程通过网络启动主机功能。

#### 3.7.1.1 方法一: OC 全局重命名强制睡眠

上一步中已经确认了你的主板是 `0D` 还是 `06`，打开 `OC little` 的 `06/0D` 补丁，选择合适自己主板的补丁集，比如我的是 `Name-6D更名.plist`。将补丁抄入自己的 `config.plist` 后重启生效。

> 全局重命名会导致其他系统无法通过 OC 引导开机，不建议使用。

------

#### 3.7.1.2 方法二: 沿用Clover版本的0D/06补丁&展示TgtBridge在OC下的用法

宪武大大做的 clover 版本的 0d/6d 补丁，其实没啥必要讲，只是有留言问了 tgtbridge 在 oc 下怎么用，那我就展示一下吧。这个补丁原理是一样的，通过重命名的方式改 `_prw`。

直接下载宪武大大的[clover hotpatch](https://github.com/daliansky/P-little/tree/master/部件补丁包/11-1-睡了即醒(0D:6D)补丁)补丁包，打开plist文件。那我们拿出一组数据来讲解怎么把它翻译成oc版本：

```
Comment      String       XHC:_PRW to XPRW
Disabled     Boolean      True//此补丁并未生效，这里要改成false才会生效
Find         5F505257         //hex转text的含义即是：_PRW Replace      58505257         //hex转text的含义即是：XPRW TgtBridge    5848435F         //hex转text的含义即是：XHC_
```

这组改名是对 `XHC` 下的 PRW 改名为` xprw`，这样的话，之前 prw 下的 `(0x6D, 0x04)` 即不生效了。而指定 xhc 的方法即是使用了 tgtbridge，因为整张 dsdt 上有几十上百个 `_PRW`，你必须通过 tgtbridge 来指定到底是哪一个部件的 `_PRW`。

那么 OC 到底怎么使用 tgtbridge 来特定某一部件下的内容重命名呢？我们先把上面一段 clover 的补丁转换成 oc 的版本先吧：

```
Comment           String        XHC:_PRW to XPRW
Count             Number                      //需要重点解释
Enabled           Boolean       True          //表示应用此补丁，不应用选False
Find              Data          5F505257      //hex转text的含义即是：_PRW
Limit             Number        0             //这个按默认即可 不去管他
Mask              Data          <>            //这个按默认即可 不去管他
OemTableId        Data          <>            //这个按默认即可 不去管他
Replace           Data          58505257      //hex转text的含义即是：XPRW
ReplaceMask       Data          <>            //这个按默认即可 不去管他
Skip              Number                      //需要重点解释
TableLength       Number        0             //这个按默认即可 不去管他
TableSignature    Data          44534454      //hex转text的含义即是：DSDT，这里按默认即可，代表对dsdt进行修改
```

这里就是一个还没全部翻译好的 oc 版改名 xhc 的 prw。那么如何定位 xhc 下的 `_prw` 呢，主要是填写 `Count` 和 `Skip`。其实 oc 的 `tgtbridge` 是通过一个个数过去来定位具体哪一个位置的。比如xhc的prw是整张dsdt里面的第55个，那 `skip` 填 `54`，意味着跳过前 `54` 个，从第 `55` 个开始执行。那执行多少次呢？执行一次 `count` 就填 1；比如你要同时改第 `55` 个和 `56` 个，那 count 就填 `2`。说了这么多，我来实操一下吧：

打开dsdt，在左下角直接搜索_PRW，就能把整张表的_PRW筛选出来了：
![截屏2019-11-08上午2.57.43.png](data:image/svg+xml;base64,PCEtLUFyZ29uTG9hZGluZy0tPgo8c3ZnIHdpZHRoPSIxIiBoZWlnaHQ9IjEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgc3Ryb2tlPSIjZmZmZmZmMDAiPjxnPjwvZz4KPC9zdmc+)

我总共数了一下，一共有56个_PRW。我们再在主内容栏上按 ⌘ +F 搜索 xhc，直接找到 xhc 的 `_PRW`，刚好我们看到我的 xhc 实在整张表的倒数第 4 个，也就是正数第 53 个：

![截屏2019-11-08上午3.00.36.png](https://i.loli.net/2020/10/31/SzvArXcH4OimtR9.png)

那么我们就可以补充完整张表了：

```
Comment          String       XHC:_PRW to XPRW
Count            Number       1
Enabled          Boolean      True
Find             Data         5F505257
Limit            Number       0
Mask             Data         <>
OemTableId       Data         <>
Replace          Data         58505257
ReplaceMask      Data         <>
Skip             Number       52
TableLength      Number       0
TableSignature   Data         44534454
```

如果你想第 53、54、55 个都改掉，那 count 就写 3，意味着顺序执行3次。好了，就这样，有问题留言。

------

#### 3.7.1.3 方法三：配合SSDT+重命名的强制睡眠补丁（推荐）

oc 不提倡用户直接全局重命名，如果真的要用重命名，也一定是搭配 ssdt 去做重命名，所以这个方法也是宪武大大和我最推荐的一种方法。

打开宪武大大的 OC-SSDT 包，找到 `0D/6D` 文件夹，打开 `SSDT-GPRW.dsl`。

```
// In config ACPI, GPRW to XPRW
// Find: 47505257 02
// Replace: 58505257 02 //这里提示你要应用这个补丁，你必须在config中的ACPI-PATCH里面加入如上重命名内容
//
DefinitionBlock ("", "SSDT", 2, "ACDT", "GPRW", 0)
{
  External(XPRW, MethodObj) //寻找dsdt表中叫做XPRW的内容，这是要你在config中先把gprw改名成xprw才会生效，这就是为什么这个补丁的重命名必须是这个ssdt和重命名一起用的原因，你第一个重命名不生效，这个ssdt也不会生效。
  Method (GPRW, 2, NotSerialized)
  {
    If (_OSI ("Darwin")) //为了不破坏dsdt完整性，这里做了系统判断，当你运行windows的时候，此ssdt不生效
     {
       If ((0x6D == Arg0)) //如果你的dsdt中是6D进行判断
       {
         Return (Package ()
         { 0x6D,
           Zero
          })
       }
 
       If ((0x0D == Arg0)) //如果你的dsdt中是0D进行判断
       {
         Return (Package ()
         { 0x0D,
           Zero
          })
        }
      }
  Return (XPRW (Arg0, Arg1)) //当运行mac系统时，如果你的dsdt中XPRW为6d，或者0d时返回为0，即屏蔽。
  }
}
```

这个 ssdt 不需要你改任何内容，打开后左上角另存为（save as), 其中文件格式(file format)必须选择 `ACPI Machine Language Binary`，文件名字就叫，记住后缀为 aml。记得将 `ssdt-gprw.aml` 放入 `EFI/OC/ACPI` 目录下，并在 `config.plist` 中加载此 aml 文件。

同时，我们需要在 `ACPI--Patch` 下增加一条全局重命名来配合此 SSDT。

```
Comment: GPRW to XPRW
Count:0
Enabled:YES
Find:<4750525702>
Limit:0
Mask:<>
OemTable:<>
Replace:<5850525702>
ReplaceMask:<>
Skip:0
TableLength:0
TableSignature:<>
```

------

### 3.8 OC官方内核补丁集介绍

这里会长期更新OC官方提供的Kernel Patch。

------

#### 3.8.1 华硕等机型开机卡F1

注意此kp补丁只对10.14.4以上系统版本生效，旧的我懒得提供了，需要留言。更好的解决卡f1的方案请参照[rtc综述](https://blog.xjn819.com/post/rtc-issues-related-to-oc.html)

```
Kernel
  Patch
     Item 0
     Base         String
     Comment      String    f1 patch （随便填，好记就行）
     Count        Number    1
     Enabled      Boolean   Yes
     Find         Data      75330fb7
     Identifier   String    com.apple.driver.AppleRTC
     Limit        Number    0
     Mask         Data      
     MaxKernel    String
     MinKernel    String
     Replace      Data      eb330fb7
     ReplaceMask  Data
     Skip         Number    0
```

------

#### 3.8.2 关机卡RTC

```
Kernel
    Patch
      Item 2
       Base         String      __ZN8AppleRTC14updateChecksumEv
       Comment      String      Disable RTC ck poweroff（随便填，好记就行）
       Count        Number      1
       Enabled      Boolean     Yes
       Find         Data
       Identifier   String      com.apple.driver.AppleRTC
       Limit        Number      0
       Mask         Data
       MaxKernel    String
       MinKernel    String
       Replace      Data        c3
       ReplaceMask  Data
       Skip         Number      0
```

------

### 3.9 300系列主板开启原生NVRAM

打开你的DSDT，搜索 `001F0000`，确定自己的

- lpc部件名字，如图示，我的lpc部件名叫做`LPC0`, 别的主板可能叫做`LPCB`，请根据实际情况记录
- lpc的路径，如图左下角红线提示，我的LPC路径在`_SB_.PC00.LPC0`

![Screenshot-2020-02-05-at-10.47.54-AM.png](https://i.loli.net/2020/11/01/fO69YhztbwBrMsd.png)

- 下载[SSDT-PMC.dsl](https://blog.xjn819.com/tools/SSDT-PMC.dsl.zip)，根据自己的dsdt编辑相关内容：

![Screenshot-2020-02-05-at-10.53.33-AM.png](https://i.loli.net/2020/11/01/gCaplW4bBY39KJs.png)

左上角另存为（save as), 其中文件格式(file format)必须选择 `ACPI Machine Language Binary`，文件名字随便写吧，我就叫 `ssdt-pmc.aml`，记住后缀为aml。记得将 `ssdt-pmc.aml` 放入 `EFI/OC/ACPI` 目录下，并在 `config.plist` 中添加加载此aml文件。

- 如果你之前模拟过nvram，请执行以下命令删除相关模拟内容：

```
# 删除文件 LogoutHook.command
sudo rm -rf $(sudo defaults read com.apple.loginwindow LogoutHook)
# 清空 LogoutHook 的触发设置
sudo defaults delete com.apple.loginwindow LogoutHook
```

- 删除EFI下的nvram.plist。
- 同时你需要对config.plist进行设置：
  - NVRAM–LegacyEnable 选择No
  - NVRAM–LegacyOverwrite 选择No
  - Booter–Quirks—-DisableVariableWrite 选择no
  - 你也许要打开NVRAM—WriteFlash 选择YES（请尽可能不要选！）

------

### 3.10 Acidanthera Debug 错误调试

此博客有很多疏漏，你可能会碰到很多奇怪的问题而无法解决。一般来说，一张开机-v的截图只能解决一些很简单的问题，一些帮助者可能通过经验判断你的错误所在，但这样的图无法定位错误，而Acidanthera提供了非常非常强大的排错功能，我们可以利用它收集错误报告，在网络上获得帮助。

如果我们需要debug报告，我们需要将所有的Acidanthera的kext以及OC bootloader替换成debug版本，所有的debug版本都会在github中提供。我们下载debug版本的Opencore，替换：

- EFI/BOOT/
  - BOOTx64.efi
- EFI/OC/Bootstrap/
  - Bootstrap.efi
- EFI/OC/Drivers/
  - OpenRuntime.efi
- EFI/OC/
  - OpenCore.efi
- 下载所有Acidanthera的debug版本kexts，并替换到EFI/OC/kexts

修改config.plist中的如下内容：

- **AppleDebug** `YES`
- **ApplePanic** `YES`
- **DisableWatchdog** `YES`
- **Target** `67`
- **DisplayLevel** `2147483714`
- **PickerMode** `Builtin`

在Config.plist/NVRAM/7C436110-AB2A-4BBB-A880-FE41995C9F82/boot-args栏目中增加

- `-liludbgall liludump=30`

保存后重启，你会得到：

- /EFI/下找到开机启动日志 (e.g. opencore-2020-11-16-083514.txt)
- /var/log下得到所有Acidanthera的kext的日志(e.g.Lilu_1.5.0_20.1.txt)

如果无法进入系统，则只需要第一份日志。

你可以通过这两份日志快速定位错误，或者在网路上寻求帮助。

------

## 4.0 OpenCore 进阶

以下内容对你正常使用黑苹果已经无关了，如果你追求更好的黑果表现，可以看下去，但这部分内容也需要你自己有更好的能力与耐心。如果你不具备足够的条件，我不建议你看下去；如果你的失误导致硬件的损坏，我也不会、也没能力负责。

------

### 4.1 CPU的变频优化

此章节对你的要求会相对高一点，并且请你具备如下条件：

- 有耐心
- CFG已经解锁（这也许不是必要条件）
- 已经打开原生电源管理。
- 此章节只适用于4代之后的CPU。
- 在调整CPU变频时，出现失误导致CPU温度过高，能有正确的处理能力保证CPU不烧毁，我对极端的后果不负责任。
- 此教程对无核显用户不友好，需要自己更多的领悟。
- 如果你不同意第五条，请不要看下去。

在Intel四代之后，苹果引入了新的内核级电源管理方式：`XCPM`（XNU CPU Power Management），这种新的管理方式可以高效地管理电源及变频。同时，苹果也推出了`HWP` (HardWare controlled Performance states)，这种技术可以快速根据特定程序的需求，作出变频转换。我们这个章节，本质上就是在加载`XCPM`的情况下，调整`HWP`来优化CPU的变频。

同时我要说的是，我在论坛上看到很多所谓的“变频”，有的甚至加载了50多个档位的变频，其实这种是完全没有意义的。我认为，变频是能在你需要的高频的时候快速进入高频状态，在关闭程序后又能很快回到低档位，换句话说，其实只需要三个档位就高了：睿频档，正常频率，以及低频档。

- 你需要搞清楚自己的cpu型号，并找到、换成与自己cpu型号最接近或者一样的白苹果型号，并且此型号必须带有`HWP`。一般新的笔记本机型都具有，台式机的话推荐iMac19.1以及Macmini8.1。可查询[此帖](https://blog.daliansky.net/A-command-to-teach-you-how-to-confirm-their-own-models-and-how-to-open-the-HWP.html)选取适合的机型。
- 执行如下命令：

```
cd ~/desktop
mkdir cpu
cd cpu
git clone https://github.com/corpnewt/CPUFriendFriend.git
git clone https://github.com/acidanthera/CPUFriend.git cp ~/desktop/cpu/CPUFriend/tools/ResourceConverter.sh ~/desktop/cpu/
CpuFriendFriend/CPUFriendFriend.command
```

- 你会看到如图的命令行，这里1 of 4代表第一段睿频的设置，以此类推，数值越大睿频越高，下面要求你填写的是最低的频率值，你想要低一点的800MHZ就填08，高一点的1300MHZ就填0D（注意大小写）![Screen-Shot-2019-12-09-at-11.28.30-AM.png](data:image/svg+xml;base64,PCEtLUFyZ29uTG9hZGluZy0tPgo8c3ZnIHdpZHRoPSIxIiBoZWlnaHQ9IjEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgc3Ryb2tlPSIjZmZmZmZmMDAiPjxnPjwvZz4KPC9zdmc+)
- 填完前两段后，它会要求你填写EPP值，EPP值越低，性能表现越强。我们是填的前两段的低频率部分，我们可以选择节能型的，比如0x80，如果你想极致性能，可以填0x00。
  ![Screen-Shot-2019-12-09-at-11.32.38-AM.png](data:image/svg+xml;base64,PCEtLUFyZ29uTG9hZGluZy0tPgo8c3ZnIHdpZHRoPSIxIiBoZWlnaHQ9IjEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgc3Ryb2tlPSIjZmZmZmZmMDAiPjxnPjwvZz4KPC9zdmc+)
- 直至你填完所有4段变频需求后，便会生成你的变频plist。我们执行以下命令:

```
cp ~/Desktop/cpu/CpuFriendFriend/Results/*.* ~/Desktop/cpu

 
 
 
```

- 我们会在桌面的CPU文件夹中找到你所需要的`ResourceConverter.sh`以及Mac-xxxxxxx.plist两个文件
- 执行以下命令生成你最终需要的`CPUFriendDataProvider.kext`,注意命令行中`Mac-AA95B1DDAB278B95.plist`，请替换成你自己的文件名，这样我们就可以在桌面的CPU文件夹下拿到`CPUFriendDataProvider.kext`。

```
cd ~/Desktop/cpu
./ResourceConverter.sh --kext ~/Desktop/cpu/Mac-AA95B1DDAB278B95.plist
```

- 我们再到CPUFriend的[release](https://github.com/acidanthera/CPUFriend/releases)页面下，下载最新的release版本，得到里面的CPUFriend.kext
- 将`CPUFriendDataProvider.kext`与`CPUFriend.kext`一起放到oc/kexts下,并在config中加载，注意：`CPUFriend.kext`应该放在`CPUFriendDataProvider.kext`的前面。
- 感谢 @请叫我官人 的帮助。完成，自行测试。

------

### 4.2 5700/XT/Redeon VII显卡的性能优化

此教程已经发于pcbeta:[点此直达](http://bbs.pcbeta.com/viewthread-1836920-1-1.html)

 [Hackintosh](https://blog.xjn819.com/tags/Hackintosh/)[OpenCore](https://blog.xjn819.com/tags/OpenCore/)

