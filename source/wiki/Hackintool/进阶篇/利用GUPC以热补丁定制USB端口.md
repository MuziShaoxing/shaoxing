---
layout: wiki
wiki: Hackintool
title: 进阶篇-利用GUPC以热补丁定制USB端口
order: 603
---
> 版权©️声明 : 本文章[神楽小白(GZ小白)的部落阁 ](https://blog.gzxiaobai.cn)
------------
## 前言

虽然之前就有用热补丁定制USB端口的方法，但那个方法需要搭配**USBAllinject.kext**使用，在受到Github中一个issue的启发后，我们发现，可以利用ACPI中的**GUPC**实现USB端口的热补丁定制。最后，通过咨询了**哞大**相关问题，发此贴，提供方法。

Github的issue链接如下：[https://github.com/daliansky/OC-little/issues/18](https://github.com/daliansky/OC-little/issues/18)

<!--more-->

## 基本原理
我们这边就以那个issue为样例进行说明

机型原始**GUPC**方法为：

```
Method (GUPC, 1, Serialized)
{
    Name (PCKG, Package (0x04)
    {
        Zero, 
        0xFF, 
        Zero, 
        Zero
    })
    PCKG [Zero] = Arg0
    Return (PCKG)
}
```

首先，我们先来了解下PkgObj的一些基本知识

在`PCKG, Package (0x04)`中，我们不难发现 **0x04** 对应了下面的四个项，也就是 `Zero`、`0xFF`、`Zero`、`Zero`这些，也就是说，Pkg下有几个项，这里的值就对应是多少，比如有三个那么就是 **0x03** (**<u>PS：这里的值为16进制</u>**)

然后，我们再来看Pkg中的项的位置：

```
···
    Name (PCKG, Package (0x04)
    {
        Zero, //第一个项的位置为：Zero
        0xFF, //第二个项的位置为：One
        Zero, //第三个项的位置为：0x03
        Zero  //第四个项的位置为：0x04
    })
    PCKG [Zero] = Arg0
    Return (PCKG)
···
```

这样子应该就一目了然了吧，以此类推下去就行，记住一点，初始位并不是 **One** 而是 **Zero**



## 实现定制

这里我们给出一个修改完成的样例：

```
DefinitionBlock ("", "SSDT", 2, "INTEL", "GUPC", 0x00000000)
{
    External (_SB.PCI0.XHC.RHUB, DeviceObj)
    External (_SB.PCI0.XHC.RHUB.XUPC, MethodObj)
    
    Scope (_SB.PCI0.XHC.RHUB)
    {
        Name (USBP, Zero)
        Method (GUPC, 1, Serialized)
        {
            If (_OSI ("Darwin"))
            {
                Name (PCKG, Package (0x04)
                {
                    0xFF, 
                    0x03, 
                    Zero, 
                    Zero
                })
                USBP += One
                If (((USBP == 0x04) || (Arg0 == Zero)))
                {
                    PCKG [Zero] = Zero
                }

                If ((((USBP == 0x04) || (USBP == 0x05)) || (USBP == 0x06)))
                {
                    PCKG [One] = 0xFF
                }

                Return (PCKG) 
            }
            Else
            {
                Return (XUPC(Arg0))
            }
        }
    }
}
```

现在我们来一一解释一下，我们要明白在ACPI中，每个端口都有对应的`_UPC`方法来返回`GUPC`的值来确定端口的**状态(开启或者关闭)**以及**类型**，`_UPC`方法见下:

```
Method (_UPC, 0, NotSerialized) 
{
    Return (GUPC(One)) 
}
```

那这个返回语句中的**One**是什么意思呢？其实这个**One**赋值给了**GUPC**方法中的**Arg0**，我们看到原来的**GUPC**方法中，有这个一句：`PCKG [Zero] = Arg0`，也就是这个端口在返回**GUPC**这个方法时。将**Arg0**赋值为了**One**，那么`PCKG [Zero] = Arg0`中，**PCKG**后面跟着的**Zero**又是什么意思呢？这个其实联系我之前讲的Pkg中**项的位置**就很好理解了，这里对应的就是**PCKG中Zero位置的项**，那么整句话的意思就是：**<u>将PCKG这个Pkg中Zero位置的项覆盖为Arg0的值</u>**

而在**GUPC**方法里的**PCKG**中，也正是**Zero位置的项**和**One位置的项**决定着端口的**状态**和**类型**：

```
···
    Name (PCKG, Package (0x04)
    {
        Zero, //Zero位置[决定端口状态]: Zero为关闭，其它值都为开启
        0xFF, //One位置 [决定端口类型]：详细对应可见下面我给出的表
        Zero, //此值为保留，必须为Zero
        Zero  //此值为保留，必须为Zero
    })
···
```

**One**位置的值所对应的**端口类型**：

```
---------------------------
//常用值
0x03  //USB3.0 Type-A
0x09  //TypeC Type C+sw 10
0xFF  //内建 专用连接器
---------------------------
//完整表
0x00  //类型”A”连接器
0x01  //Mini-AB连接器
0x02  //ExpressCard  USB智能卡
0x03  //USB3标注A连接器
0x04  //USB3标注B连接器
0x05  //USB3 Micro-B连接器
0x06  //USB3 Micro-AB连接器
0x07  //USB3 Micro-B连接器
0x08  //USB Type-C (只有 USB 2)
0x09  //USB Type-C (带有转向器)
0x0A  //USB Type-C (不带转向器)
0xFF  //专用连接器 内置
---------------------------
```

好了，知道了这些我们就可以正式开始着手定制我们的USB端口了。

你们看我给出的完整补丁里，定义了一个**USBP**，并赋值为了**Zero**，然后又在GUPC这个方法中添加了语句：`USBP += One`，让**USBP**的值加上1，其实定义这个**USBP**其实是为了帮我们**定位对应的端口**，由于**GUPC**方法是**Serialized**，所以每次在一个端口调用完**GUPC**后，它并不会重置，所以我们可以添加一个**USBP**，每被一个端口调用一次，**USBP**的值就增加1，那么当第一个端口调用**GUPC**时，**USBP**为**1**，第二个端口再调用时，**USBP**的值就在1的基础上再加1，也就是**2**。

那么就可以很好理解了，这样的话，每一个端口都会按顺序对应一个相应的**USBP**的值。

接下来，我们在添加判断语句来确定每个端口的**状态**和**类型**(见上面给出的完整补丁)：

```
 ···               
     If (((USBP == 0x04) || (Arg0 == Zero)))
     {
         PCKG [Zero] = Zero
     }

     If ((((USBP == 0x04) || (USBP == 0x05)) || (USBP == 0x06)))
     {
         PCKG [One] = 0xFF
     }
···
```

我们来先来理解一下第一段判断语句的意思，就是：

- 当 **USBP = 0x04 **或者 **Arg0 = Zero** 的时候，将**PCKG**中**Zero位置**的值覆盖为**Zero**，也就是禁用**第四个端口**和**返回的Arg0的值为Zero的端口**。

我们再来看第二段判断语句的意思：

- 当 **USBP  = 0x04** 或者 **USBP  = 0x05** 或者 **USBP  = 0x06** 的时候，将**PCKG**中**One位置**的项的值覆盖为**0xFF**，也就是把**第四、五、六端口**的类型定义为**内建**。

当然，我们可以根据自己的需求去写判断语句，以达到我们想定制的效果，哪些端口开，哪些端口关，并定义这些端口的类型。

最后我们再返回**PCKG**就OK了，添加好`If (_OSI ("Darwin"))`语句来判定在**macOS**系统下生效，最后我们在**Config**中补充**重命名**：

```
Comment: USB GUPC to XUPC
Find: 47 55 50 43 09
Replace: 58 55 50 43 09
```

## 结语

好了，这也是这个教程的主要部分了，希望能给大家定制USB以一个新的方法思路！

加入博主的Hackintosh交流群：`679838716`

