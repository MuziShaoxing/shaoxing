---
layout: wiki
wiki: Hackintool
title: 进阶篇-计算Slide解决内存报错
order: 605
---
> 版权©️声明 : 本文章[神楽小白(GZ小白)的部落阁 ](https://blog.gzxiaobai.cn)
------------
## 前言
如果你在安装黑苹果的过程中，遇到了内存报错，那么你可能需要通过**计算Slide值并注入**来解决这个问题
<!--more-->
**KASLR (Kernel Address Space Layout Randomization)**：内核地址空间布局随机化，是 macOS 所使用的一项内存管理技术，它会在内存基址上加一个 Slide 值，用于保护内核安全。

>Slide 的有效范围是 8 - 255，转化为 16 进制就是 8 - FF ，乘 200000（16 进制）得出的内存基址 Start 范围为 1000000 - 1FE00000

## 问题

如果你遇到如下代码，在安装过程中。

```
Error allocating 0x0x116F6 pages at 0x00000000093eb000 alloc type 2
```

那么恭喜，这是内存报错，对于笔记本而言，一般可以通过更换**内存补丁**来解决。但对于自由度较高的台式机来说，就没那么好了，那么我们就来计算**Slide值**，启用**KASLR**内存管理技术了。

## 解决方案

我们继续看上面的那一串代码，我们需要记录的就是**0x0x116F6**，也就是**Page值**

进入 **clover**，打开 **UEFI Shell 64** 界面，输入 **memmap -b**，找到第一个 **Star**t 大于 **1000000**（**对应 Slide 最小值 8**）且 **Page** 值大于 **0x116F6** （**出错的 Page 值**） 的 **Available** 类型数据，如下所示

```
Available 00000000 1000B000 00000000 5F04FFFF 00000000 0004F045 00000000 0000000F
```

可见 **1000B000** 在这个范围内，使用**十六进制计算器**用这个值除 **200000**（**16 进制**）得出的值**转为十进制向上取整**即可

例如 例如 **1000B000（十六进制）/ 200000（十六进制）= 128.02（十进制）向上取整为 129**，接下来我们将 **slide=129** 添加到引导参数中，问题基本上都能解决

在线十六进制计算器：[点我！](http://www.99cankao.com/digital-computation/hex-calculator.php)

## 参考教程
[XStar-Dev's Blog](https://xstar-dev.github.io/hackintosh_primary/Memory_Exception.html)

加入博主的Hackintosh交流群：`679838716`

