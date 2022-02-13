---
layout: wiki
wiki: Hackintool
title: RTC综述 
order: 29
---
> 版权©️声明 : 本文章出自 **Xjn´s Blog** [RTC综述](https://blog.xjn819.com/post/rtc-issues-related-to-oc.html)
------------

这篇文章试图教育用户解决RTC(CMOS)记忆体相关的错误导致无法开机，卡F1，无法关机，时钟停止，无法唤醒等问题。此文章为《使用OpenCore引导黑苹果》的补充内容，因原文中RTC相关内容较为散乱，而特意补充。

------

> 特别提醒：在使用以下方式修复rtc的过程之前，强烈建议先短接主板CMOS以及清除NVRAM后再进行操作！NVRAM和CMOS存储位置不同，请确定两件事都做了！！

------

## RTC的问题表现

- 华硕等主板开机卡F1
- 开机卡在PCI Configuration代码处
- 睡眠后唤醒奔溃，得到的错误报告为：Sleep Wake Failure in EFI
- 无法关机
- 电脑时钟不走，或者睡眠唤醒后时钟不走

------

## RTC如何工作

RTC为l2c下的从设备，rtc为系统提供时间，电源，硬件信息等指示数据，l2c主动联系从设备rtc获取信息，反馈给系统。这些信息都被注册在rtc的各个内存位置上，这些内存地址对应的数据可通过OC-liilte或者搜索自己主板型号的intel datasheet获得。

> 举例：
> 系统设定一个自动关机的时间，比如22:20分，此信息通过系统trigger到rtc，l2c扫到rtc信息，则自动关机。

------

## 苹果系统下RTC的问题如何产生？

问题主要是因为Apple。

- Apple公司使用自己定义的Apple RTC，而普通主板可能引用了最新的AWAC装置来代替传统RTC而导致无法开机。
- Apple公司使用自己定义的Apple RTC，Apple RTC记录的内存范围可能不被我们普通的主板所支持，超出了我们普通主板0x70-0x78范围而导致了错误。

------

## 如何解决上述问题

对于《苹果系统下RTC的问题如何产生？》，第一个问题是这样的：一些具有AWAC的设备我们可能需要禁用AWAC来启用Legacy RTC。这里可通过[OC-Little](https://github.com/daliansky/OC-little/tree/master/03-二进制更名与预置变量/补丁库)包中的禁用AWAC来实现。其中SSDT-AWAC.dsl更适用于主板DSDT代码特别多的主板，请根据情况二选一并转换成aml后使用。

------

对于第二个问题，它可能带来的影响包括时钟不走，关机不断电，开机卡f1，无法唤醒，唤醒崩溃等。这种问题就像我之前说的，是因为apple rtc写入到了普通主板rtc不支持的范围而导致的。

我之前在主文章有写到通过[二进制补丁](https://github.com/RehabMan/HP-ProBook-4x30s-DSDT-Patch/blob/master/config_parts/config_master.plist#L291L296)来解决开机卡F1，但这种方式其实是不妥当的，这是因为：

- 这种补丁会因为系统版本的更新而失效
- 并不能控制Efiboot来写入RTC
- 卡F1的因素过多，而二进制补丁不可能具有通用性

因此，OC团队提供了三种方式来更好的解决RTC引起的各种问题。

- 提供DisableRtcChecksum选项来忽略RTC地址中的0x58-0x59范围。但遗憾的是此quirk只适用于0x58-0x59地址损坏的rtc情况，并不具备通用性。
- ACDT团队提供了[RTCMemoryFixup.kext](https://github.com/acidanthera/RTCMemoryFixup/releases)让用户可以自主选择所有你想屏蔽的地址。此kext需要用二分法来使用。
- 将此kext放入OC/Kexts下面，并在config中加载它。
- 一般来说，我们CMOS的总内存池是从00-FF（这个是16进制，换算成10进制就是从0-255)，我们可以通过增加boot-args:rtcfx_exclude=00-FF来完全屏蔽cmos（当然这样写你完全失去了cmos记忆的功能了）
- 我们需要通过二分法来定位你出错的cmos位置。把00-FF分成两部分，也就是00-7F以及80-FF。我们分别填一次rtcfx_exclude=00-7F以及rtcfx_exclude=80-FF，试试看问题有没有解决。比如说我使用的rtcfx_exclude=80-FF是解决了，那我们继续对80-FF进行拆分为：0x80-0xBF 和 0xC0-0xFF。以此类推，直到你拆分到最后的那一段位置为止。
- ACDT团队提供了写入NVRAM的方式来屏蔽RTC地址。如图，RTC-blacklist中 8586878889 代表屏蔽85 86 87 89的RTC地址，如果屏蔽85以及86则填写8586。注16进制。    
  ![rtc-blacklist.png](https://i.loli.net/2020/11/02/4SjaDbtdNivyOVA.png)

------

## 特殊情况

有两个非常特殊的情况：

- 一些主板本身的DSDT就把RTC的地址写错了，我们需要更正。比如，华硕299的主板没有对rtc的0x72以及0x73进行映射，源dsdt中的资源分配如下代码。0x70只加到了0x72之前，从0x74位开始加到了0x78之前，也就是0x72以及0x73被忽略。因此需要官方的ssdt对rtc的资源进行重新分配

```
Device (RTC)
{
    Name (_HID, EisaId ("PNP0B00") /* AT Real-Time Clock */)  // _HID: Hardware ID
    Name (_CRS, ResourceTemplate ()  // _CRS: Current Resource Settings
    {
        IO (Decode16,
            0x0070,             // Range Minimum
            0x0070,             // Range Maximum
            0x01,               // Alignment
            0x02,               // Length
            )
        IO (Decode16,
            0x0074,             // Range Minimum
            0x0074,             // Range Maximum
            0x01,               // Alignment
            0x04,               // Length
            )
        IRQNoFlags ()
            {8}
    })
```

- Smbus是一种可能已经被淘汰的总线方式，此部件在很多新的机型中已经不再被需要。但经证实在过往的一些mac版本中需要激活它才能进入睡眠唤醒，这是一种很奇怪的现象，但是一般来说此补丁不该被需要。请注意原文中的`0x57`应该根据自己的主板来决定。比如我的x299主板应该搜索`x299 intel datasheet`，获得自己主板的`datasheet`后，得知自己Smbus串口的位置为`0xc6`，替换原文中的所有`0x57`为`0xc6`。此SSDT应只用于debug。

```
/*
 * SMBus compatibility table.
 */
DefinitionBlock ("", "SSDT", 2, "ACDT", "MCHCSBUS", 0x00000000)
{
    External (_SB_.PCI0, DeviceObj)
    External (_SB_.PCI0.SBUS, DeviceObj)
 
    Scope (_SB.PCI0)
    {
        Device (MCHC)
        {
            Name (_ADR, Zero)  // _ADR: Address
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
 
    Device (_SB.PCI0.SBUS.BUS0)
    {
        Name (_CID, "smbus")  // _CID: Compatible ID
        Name (_ADR, Zero)  // _ADR: Address
        Device (DVL0)
        {
            Name (_ADR, 0x57)  // _ADR: Address
            Name (_CID, "diagsvault")  // _CID: Compatible ID
            Method (_DSM, 4, NotSerialized)  // _DSM: Device-Specific Method
            {
                If (!Arg2)
                {
                    Return (Buffer (One)
                    {
                         0x57                                             // W
                    })
                }
 
                Return (Package (0x02)
                {
                    "address", 
                    0x57
                })
            }
        }
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
 
    Method (DTGP, 5, NotSerialized)
    {
        If ((Arg0 == ToUUID ("a0b5b7c6-1318-441c-b0c9-fe695eaf949b")))
        {
            If ((Arg1 == One))
            {
                If ((Arg2 == Zero))
                {
                    Arg4 = Buffer (One)
                        {
                             0x03                                             // .
                        }
                    Return (One)
                }
 
                If ((Arg2 == One))
                {
                    Return (One)
                }
            }
        }
 
        Arg4 = Buffer (One)
            {
                 0x00                                             // .
            }
        Return (Zero)
    }
}
```

------

## References

- Dortania Team, (2020).,. available at: https://dortania.github.io/OpenCore-Post-Install/misc/rtc.html#finding-our-bad-rtc-region, last accessed at 10 Oct 2020.
- OC little, (2020)., <03-二进制更名与预置变量>. available at:https://github.com/daliansky/OC-little/tree/master/03-二进制更名与预置变量, last accessed at 10 Oct 2020.
- Acidanthera (2020)., available at: https://github.com/acidanthera/OpenCorePkg/tree/master/Docs/AcpiSamples , last accessed at 10 Oct 2020.