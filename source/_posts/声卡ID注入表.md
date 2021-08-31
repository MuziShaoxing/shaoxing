---
title: 黑苹果声卡ID注入表
abbrlink: bdd0d26d
---




> 版权©️声明 : 此文章出自 **[GitHub_AppleALC支持编译码](https://github.com/acidanthera/AppleALC/wiki/Supported-codecs)** 
------------

## AppleALC

一个开源的内核扩展,为非官方的声卡提供支持的Codec,无需修改任何系统文件,来启用原生macOS高清音频.

### 特性

- 在系统安装阶段即可使用数字或模拟音频.
- 支持恢复模式与安装模式.
- 自动加载声卡Codec.
- 启用Apple官方不支持的编解码器 (无论是内置还是外置的声卡设备).
- 任意的kext修改补丁.
- 自定义设备Layout ID号与支持平台.
- 工作在 SIP 模式 / El Capitan 系统.
- 当前版本兼容: 10.8-11.

### 如何安装
现在已经在WIKI上提供了最简单的安装介绍 [点我](https://github.com/vit9696/AppleALC/wiki).
想下载最新版本的AppleALC驱动程序? 点它跳转到下载页→[Releases](https://github.com/acidanthera/AppleALC/releases).

### 我如何为这个AppleALC提供更多的Codec数据来适配更多的机器?
如果你想为更多不同的机器适配不同的Codec,你需要提供你的配置文件. 请阅读[基本指南](https://github.com/vit9696/AppleALC/wiki)获取更多信息. 如果你是一个程序开发者想要贡献你的代码,可以看到在很多代码文件头部就有很重要的AppleDOC注释供你参考.

### 声卡ID注入表
 - 更新时间2021-08-23

| Vendor        | Codec                                                        | Revisions and layouts                                        | MinKernel | MaxKernel |
| ------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | --------- | --------- |
| AnalogDevices | [AD1984](https://github.com/acidanthera/AppleALC/tree/master/Resources/AD1984) | 0x100400, layout 11                                          | 13 (10.9) | —         |
| AnalogDevices | [AD1984A](https://github.com/acidanthera/AppleALC/tree/master/Resources/AD1984A) | 0x100400, layout 11, 13, 44                                  | 13 (10.9) | —         |
| AnalogDevices | [AD1988A](https://github.com/acidanthera/AppleALC/tree/master/Resources/AD1988A) | layout 12                                                    | 13 (10.9) | —         |
| AnalogDevices | [AD1988B](https://github.com/acidanthera/AppleALC/tree/master/Resources/AD1988B) | layout 5, 7, 12                                              | 13 (10.9) | —         |
| AnalogDevices | [AD2000B](https://github.com/acidanthera/AppleALC/tree/master/Resources/AD2000B) | layout 5, 7                                                  | 13 (10.9) | —         |
| Realtek       | [ALC1150](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC1150) | 0x100001, layout 1, 2, 3, 5, 7, 99                           | 12 (10.8) | —         |
| Realtek       | [ALC1220](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC1220) | 0x100101, 0x100003, layout 1, 2, 3, 5, 7, 11, 13, 15, 16, 17, 21, 27, 28, 29, 30, 34, 35, 98, 99, 100 | 12 (10.8) | —         |
| Realtek       | [ALC215](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC215) | 0x100002, layout 18                                          | 13 (10.9) | —         |
| Realtek       | [ALC221](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC221) | 0x100003, 0x100103, layout 11, 15, 88                        | 12 (10.8) | —         |
| Realtek       | [ALC222](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC222) | 0x100001, layout 11                                          | 12 (10.8) | —         |
| Realtek       | [ALC225/ALC3253](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC225) | layout 28, 30, 33, 90                                        | 13 (10.9) | —         |
| Realtek       | [ALC230](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC230) | layout 13, 20                                                | 13 (10.9) | —         |
| Realtek       | [ALC233/ALC3236](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC233) | 0x100003, layout 3, 4, 5, 13, 21, 27, 28, 29, 32, 33         | 13 (10.9) | —         |
| Realtek       | [ALC235](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC235) | layout 3, 11, 12, 14, 15, 16, 17, 18, 21, 22, 24, 28, 35, 37, 99 | 13 (10.9) | —         |
| Realtek       | [ALC236](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC236) | 0x100001, 0x100002, layout 3, 11, 12, 13, 14, 15, 16, 18, 54, 99 | 13 (10.9) | —         |
| Realtek       | [ALC245](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC245) | layout 11, 12, 13                                            | 13 (10.9) | —         |
| Realtek       | [ALC255/ALC3234](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC255) | layout 3, 11, 13, 15, 17, 18, 20, 21, 27, 28, 29, 30, 31, 66, 71, 82, 86, 96, 99, 100 | 13 (10.9) | —         |
| Realtek       | [ALC256/ALC3246](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC256) | 0x100002, layout 5, 11, 13, 14, 16, 17, 19, 21, 22, 23, 28, 56, 57, 66, 67, 69, 70, 76, 77, 88, 97 | 13 (10.9) | —         |
| Realtek       | [ALC257](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC257) | 0x100001, layout 11, 18, 86, 99, 100                         | 13 (10.9) | —         |
| Realtek       | [ALC260](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC260) | layout 11, 12                                                | 13 (10.9) | —         |
| Realtek       | [ALC262](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC262) | 0x100100, 0x100302, 0x100202, layout 7, 11, 12, 13, 28, 66   | 12 (10.8) | —         |
| Realtek       | [ALC268](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC268) | layout 3                                                     | 13 (10.9) | —         |
| Realtek       | [ALC269/ALC271X](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC269) | 0x100203, 0x100004, 0x100202, 0x100100, layout 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 27, 28, 29, 30, 32, 33, 35, 40, 44, 45, 47, 55, 58, 66, 76, 77, 88, 91, 93, 99, 100, 127, 128, 188 | 12 (10.8) | —         |
| Realtek       | [ALC270](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC270) | 0x100100, layout 3, 4, 21, 27, 28                            | 13 (10.9) | —         |
| Realtek       | [ALC272](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC272) | 0x100001, 0x100002, layout 3, 12, 18, 21                     | 13 (10.9) | —         |
| Realtek       | [ALC274](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC274) | 0x100004, layout 21, 28, 35                                  | 13 (10.9) | —         |
| Realtek       | [ALC275](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC275) | 0x100008, 0x100005, layout 3, 13, 28                         | 13 (10.9) | —         |
| Realtek       | [ALC280](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC280) | layout 3, 4, 11, 13, 15, 16, 17, 21                          | 13 (10.9) | —         |
| Realtek       | [ALC282](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC282) | 0x100003, layout 3, 4, 13, 21, 22, 27, 28, 29, 41, 43, 51, 76, 86, 127 | 12 (10.8) | —         |
| Realtek       | [ALC283](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC283) | layout 1, 3, 11, 13, 15, 44, 45, 66, 88                      | 13 (10.9) | —         |
| Realtek       | [ALC284](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC284) | layout 3                                                     | 13 (10.9) | —         |
| Realtek       | [ALC285](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC285) | layout 11, 21, 31, 52, 61, 71                                | 13 (10.9) | —         |
| Realtek       | [ALC286](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC286) | 0x100002, 0x100003, layout 3, 11                             | 13 (10.9) | —         |
| Realtek       | [ALC287](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC287) | layout 11                                                    | 13 (10.9) | —         |
| Realtek       | [ALC288](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC288) | layout 3, 13, 23                                             | 13 (10.9) | —         |
| Realtek       | [ALC289](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC289) | layout 11, 15, 23, 87, 99                                    | 13 (10.9) | —         |
| Realtek       | [ALC290/ALC3241](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC290) | layout 3, 4, 10, 15, 28                                      | 13 (10.9) | —         |
| Realtek       | [ALC292](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC292) | layout 12, 15, 18, 28, 32, 55                                | 13 (10.9) | —         |
| Realtek       | [ALC293](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC293) | layout 11, 28, 29, 30                                        | 13 (10.9) | —         |
| Realtek       | [ALC294](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC294) | layout 11, 12, 13, 21, 22, 28, 66                            | 13 (10.9) | —         |
| Realtek       | [ALC295](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC295) | layout 1, 3, 13, 14, 15, 21, 22, 23, 24, 28, 77              | 13 (10.9) | —         |
| Realtek       | [ALC298](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC298) | 0x100101, 0x100103, layout 3, 11, 13, 16, 21, 22, 28, 29, 30, 32, 47, 66, 72, 99 | 13 (10.9) | —         |
| Realtek       | [ALC299](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC299) | 0x100002, layout 21, 22                                      | 13 (10.9) | —         |
| Realtek       | [ALC662](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC662) | 0x100101, 0x100300, layout 5, 7, 11, 12, 13, 15, 16, 17, 18, 66 | 13 (10.9) | —         |
| Realtek       | [ALC663](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC663) | 0x100001, 0x100002, layout 3, 4, 15, 28, 99                  | 13 (10.9) | —         |
| Realtek       | [ALC665](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC665) | layout 12, 13                                                | 13 (10.9) | —         |
| Realtek       | [ALC668](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC668) | 0x100003, layout 3, 20, 27, 28, 29                           | 13 (10.9) | —         |
| Realtek       | [ALC670](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC670) | 0x100002, layout 12                                          | 13 (10.9) | —         |
| Realtek       | [ALC671](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC671) | layout 12, 15, 16, 88                                        | 13 (10.9) | —         |
| Realtek       | [ALC700](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC700) | layout 11                                                    | 13 (10.9) | —         |
| Realtek       | [ALC882](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC882) | layout 5, 7                                                  | 13 (10.9) | —         |
| Realtek       | [ALC883](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC883) | 0x100002, layout 7                                           | 13 (10.9) | —         |
| Realtek       | [ALC885](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC885) | 0x100101, 0x100103, layout 1, 12, 13, 15, 48, 50, 53, 56, 58, 60, 62, 63, 64, 65, 67, 70, 73, 74 | 13 (10.9) | —         |
| Realtek       | [ALC887](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC887) | 0x100202, 0x100302, layout 1, 2, 3, 5, 7, 11, 12, 13, 17, 18, 20, 33, 40, 50, 52, 53, 87, 99 | 13 (10.9) | —         |
| Realtek       | [ALC888/ALC1200](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC888) | 0x100001, 0x100101, 0x100202, 0x100302, layout 1, 2, 3, 4, 5, 7, 11, 27, 28, 29 | 13 (10.9) | —         |
| Realtek       | [ALC889](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC889) | 0x100004, layout 1, 2, 3, 11, 12                             | 13 (10.9) | —         |
| Realtek       | [ALC891/ALC867](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC891) | 0x100002, layout 11, 13                                      | 12 (10.8) | —         |
| Realtek       | [ALC892](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC892) | 0x100302, layout 1, 2, 3, 4, 5, 7, 12, 15, 16, 17, 18, 20, 22, 28, 31, 90, 92, 97, 99, 100 | 13 (10.9) | —         |
| Realtek       | [ALC897](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC897) | 0x100402, layout 66, 69                                      | 13 (10.9) | —         |
| Realtek       | [ALC898/ALC899](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALC898) | 0x100003, layout 1, 2, 3, 5, 7, 11, 13, 65, 66, 98, 99, 101  | 13 (10.9) | —         |
| Realtek       | [ALCS1200A](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALCS1200A) | 0x100001, layout 1, 2, 3, 11, 49, 50, 51, 69                 | 12 (10.8) | —         |
| Realtek       | [ALCS1220A](https://github.com/acidanthera/AppleALC/tree/master/Resources/ALCS1220A) | layout 1, 2, 3, 5, 7, 11, 20, 21                             | 12 (10.8) | —         |
| Creative      | [CA0132](https://github.com/acidanthera/AppleALC/tree/master/Resources/CA0132) | 0x100918, layout 0, 1, 2, 3, 4, 5, 6, 7, 9, 10, 11, 12, 99   | 13 (10.9) | —         |
| CirrusLogic   | [CS4206](https://github.com/acidanthera/AppleALC/tree/master/Resources/CS4206) | 0x100103, 0x100301, 0x100302, layout 1, 3, 9, 11, 13, 18, 24, 28, 29, 31, 32, 33, 35, 39, 61, 71, 75, 76, 77, 78, 79, 81, 84, 91, 98, 99 | —         | —         |
| CirrusLogic   | [CS4210](https://github.com/acidanthera/AppleALC/tree/master/Resources/CS4210) | 0x100101, layout 13                                          | 13 (10.9) | —         |
| CirrusLogic   | [CS4213](https://github.com/acidanthera/AppleALC/tree/master/Resources/CS4213) | 0x100100, layout 28                                          | 13 (10.9) | —         |
| Conexant      | [CX20561](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX20561) | 0x100000, layout 11                                          | 13 (10.9) | —         |
| Conexant      | [CX20583](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX20583) | layout 3                                                     | 13 (10.9) | —         |
| Conexant      | [CX20585](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX20585) | layout 3, 13                                                 | 13 (10.9) | —         |
| Conexant      | [CX20588](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX20588) | layout 3                                                     | 13 (10.9) | —         |
| Conexant      | [CX20590](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX20590) | 0x100000, 0x100002, 0x100003, layout 3, 12, 13, 14, 28       | 13 (10.9) | —         |
| Conexant      | [CX20632](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX20632) | 0x100100, layout 20, 23, 28                                  | 13 (10.9) | —         |
| Conexant      | [CX20641](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX20641) | layout 11, 13                                                | 13 (10.9) | —         |
| Conexant      | [CX20642](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX20642) | layout 11, 13                                                | 13 (10.9) | —         |
| Conexant      | [CX20722](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX20722) | layout 3                                                     | 13 (10.9) | —         |
| Conexant      | [CX20724](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX20724) | layout 3, 13                                                 | 13 (10.9) | —         |
| Conexant      | [CX20751/CX20752](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX20751_2) | 0x100100, 0x100001, layout 3, 21, 28                         | 13 (10.9) | —         |
| Conexant      | [CX20753/CX20754](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX20753_4) | layout 3, 14, 15, 21                                         | 13 (10.9) | —         |
| Conexant      | [CX20755](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX20755) | layout 3                                                     | 13 (10.9) | —         |
| Conexant      | [CX20756](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX20756) | layout 3, 13                                                 | 13 (10.9) | —         |
| Conexant      | [CX20757](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX20757) | layout 3, 28                                                 | 13 (10.9) | —         |
| Conexant      | [CX8050](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX8050) | layout 3, 13                                                 | 13 (10.9) | —         |
| Conexant      | [CX8070/CX11880](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX8070) | layout 15                                                    | 13 (10.9) | —         |
| Conexant      | [CX8150](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX8150) | layout 21, 22                                                | 13 (10.9) | —         |
| Conexant      | [CX8200](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX8200) | layout 3, 15, 21, 23, 80                                     | 13 (10.9) | —         |
| Conexant      | [CX8400](https://github.com/acidanthera/AppleALC/tree/master/Resources/CX8400) | layout 12                                                    | 13 (10.9) | —         |
| IDT           | [IDT92HD66C3/65](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD66C3_65) | layout 3                                                     | 13 (10.9) | —         |
| IDT           | [IDT92HD71B7X](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD71B7X) | layout 3                                                     | 13 (10.9) | —         |
| IDT           | [IDT92HD73C1X5](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD73C1X5) | layout 19, 21                                                | 13 (10.9) | —         |
| IDT           | [IDT92HD73E1X5](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD73E1X5) | layout 15                                                    | 13 (10.9) | —         |
| IDT           | [IDT92HD75B2X5](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD75B2X5) | layout 3                                                     | 13 (10.9) | —         |
| IDT           | [IDT92HD75B3X5](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD75B3X5) | layout 3                                                     | 13 (10.9) | —         |
| IDT           | [IDT92HD81B1C5](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD81B1C5) | layout 3, 11                                                 | 13 (10.9) | —         |
| IDT           | [IDT92HD81B1X5](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD81B1X5) | layout 3, 11, 12, 20, 21, 28                                 | 13 (10.9) | —         |
| IDT           | [IDT92HD87B1](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD87B1) | layout 3                                                     | 13 (10.9) | —         |
| IDT           | [IDT92HD87B1/3](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD87B1_3) | 0x100205, layout 12, 13                                      | 13 (10.9) | —         |
| IDT           | [IDT92HD87B2/4](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD87B2_4) | layout 13                                                    | 13 (10.9) | —         |
| IDT           | [IDT92HD90BXX](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD90BXX) | layout 3, 12                                                 | 13 (10.9) | —         |
| IDT           | [IDT92HD91BXX](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD91BXX) | 0x100102, 0x100303, layout 3, 12, 13, 33, 84                 | 13 (10.9) | —         |
| IDT           | [IDT92HD93BXX](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD93BXX) | 0x100203, layout 12                                          | 13 (10.9) | —         |
| IDT           | [IDT92HD95](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD95) | layout 11, 12, 14                                            | 13 (10.9) | —         |
| IDT           | [IDT92HD99BXX](https://github.com/acidanthera/AppleALC/tree/master/Resources/IDT92HD99BXX) | layout 3                                                     | 13 (10.9) | —         |
| SigmaTel      | [STAC9200](https://github.com/acidanthera/AppleALC/tree/master/Resources/STAC9200) | 0x102201, layout 11                                          | 8 (10.4)  | —         |
| SigmaTel      | [STAC9205](https://github.com/acidanthera/AppleALC/tree/master/Resources/STAC9205) | 0x100204, layout 11                                          | 8 (10.4)  | —         |
| SigmaTel      | [STAC9872AK](https://github.com/acidanthera/AppleALC/tree/master/Resources/STAC9872AK) | 0x100201, layout 12                                          | 12 (10.8) | —         |
| VIA           | [VT1705](https://github.com/acidanthera/AppleALC/tree/master/Resources/VT1705) | 0x100000, layout 21                                          | 13 (10.9) | —         |
| VIA           | [VT1802](https://github.com/acidanthera/AppleALC/tree/master/Resources/VT1802) | 0x100000, layout 3, 33, 65                                   | 13 (10.9) | —         |
| VIA           | [VT2020/VT2021](https://github.com/acidanthera/AppleALC/tree/master/Resources/VT2020_2021) | 0x100100, layout 5, 7, 9, 13                                 | 13 (10.9) | —         |

### 控制器补丁程序

| Vendor | Patch for not native                                         | Device | Model   | MinKernel  | MaxKernel  |
| ------ | ------------------------------------------------------------ | ------ | ------- | ---------- | ---------- |
| NVIDIA | [NVIDIA HDMI for GK208 in 10.13.4+](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x0E0F | —       | 17 (10.13) | —          |
| NVIDIA | [NVIDIA HDMI for GM200 in 10.13.4 - 10.13.6](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x0FB0 | —       | 17 (10.13) | 17 (10.13) |
| NVIDIA | [NVIDIA HDMI for GP108 in 10.13.4 - 10.13.6](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x0FB8 | —       | 17 (10.13) | 17 (10.13) |
| NVIDIA | [NVIDIA HDMI for GP107 in 10.13.4 - 10.13.6](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x0FB9 | —       | 17 (10.13) | 17 (10.13) |
| NVIDIA | [NVIDIA HDMI for GM206 in 10.13.4 - 10.13.6](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x0FBA | —       | 17 (10.13) | 17 (10.13) |
| NVIDIA | [NVIDIA HDMI for GM204 in 10.13.4 - 10.13.6](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x0FBB | —       | 17 (10.13) | 17 (10.13) |
| NVIDIA | [NVIDIA HDMI for GM107 in 10.13.4 - 10.13.6](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x0FBC | —       | 17 (10.13) | 17 (10.13) |
| NVIDIA | [NVIDIA HDMI for GP102 in 10.13.4 - 10.13.6](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x10EF | —       | 17 (10.13) | 17 (10.13) |
| NVIDIA | [NVIDIA HDMI for GP104 in 10.13.4 - 10.13.6](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x10F0 | —       | 17 (10.13) | 17 (10.13) |
| NVIDIA | [NVIDIA HDMI for GP106 in 10.13.4 - 10.13.6](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x10F1 | —       | 17 (10.13) | 17 (10.13) |
| AMD    | [AMD R9 290X HDMI](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0xAAC8 | —       | 15 (10.11) | —          |
| AMD    | [AMD R9 Fury HDMI Audio](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0xAAE8 | —       | 15 (10.11) | —          |
| AMD    | [AMD Vega-M HDMI](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0xAB08 | —       | 15 (10.11) | —          |
| AMDZEN | [AMD Zen Audio Controller 0x1457](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x1457 | —       | —          | —          |
| AMDZEN | [AMD Zen Audio Controller 0x1487](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x1487 | —       | —          | —          |
| AMDZEN | [AMD Zen Audio Controller 0x15E3](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x15E3 | —       | —          | —          |
| Intel  | [HD4600 HDMI Audio](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x0C0C | —       | 13 (10.9)  | —          |
| Intel  | [Atom Z36xxx/Z37xxx Audio Controller](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x0F04 | —       | 13 (10.9)  | —          |
| Intel  | [Z97 HDEF controller in 10.9](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x8CA0 | —       | 13 (10.9)  | 13 (10.9)  |
| Intel  | [X99 HDEF controller 0x8D20](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x8D20 | —       | 13 (10.9)  | —          |
| Intel  | [X99 HDEF controller 0x8D21](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x8D21 | —       | 13 (10.9)  | —          |
| Intel  | [100 Series (0xA170) Mobile PCH HD Audio](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0xA170 | Laptop  | 15 (10.11) | —          |
| Intel  | [WhiskeyLake Mobile PCH HD Audio](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x9DC8 | Laptop  | 16 (10.12) | —          |
| Intel  | [Intel NUC8 PCH HD Audio](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x9DC8 | Desktop | 16 (10.12) | —          |
| Intel  | [200 Series Mobile PCH HD Audio](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0xA171 | —       | 16 (10.12) | —          |
| Intel  | [200 Series PCH HD Audio](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0xA2F0 | —       | 16 (10.12) | —          |
| Intel  | [300 Series PCH HD Audio in 10.12 - 10.13](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0xA348 | —       | 16 (10.12) | 17 (10.13) |
| Intel  | [C620 Series PCH HD Audio](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0xA1F0 | —       | 19 (10.15) | —          |
| Intel  | [400 Series(0xA3F0) PCH HD Audio](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0xA3F0 | —       | 19 (10.15) | —          |
| Intel  | [400 Series PCH HD Audio](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x06C8 | —       | 19 (10.15) | —          |
| Intel  | [400 Series PCH-LP HD Audio](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x02C8 | —       | 19 (10.15) | —          |
| Intel  | [Icelake Smart Sound Technology Audio Controller](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x34C8 | —       | 19 (10.15) | —          |
| Intel  | [500 Series(0xF0C8) PCH HD Audio](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0xF0C8 | —       | 19 (10.15) | —          |
| Intel  | [500 Series(0x43C8) PCH HD Audio](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0x43C8 | —       | 19 (10.15) | —          |
| Intel  | [400 Series(0xF1C8) PCH HD Audio](https://github.com/acidanthera/AppleALC/blob/master/Resources/Controllers.plist) | 0xF1C8 | —       | 19 (10.15) | —          |