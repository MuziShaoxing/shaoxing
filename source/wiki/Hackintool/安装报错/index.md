---
layout: wiki
wiki: Hackintool
order: 103
title: 安装报错
---


> 版权©️声明 : 本站作者收集收录

------------
## Recovery下报错

![QpZpeb](https://cdn.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/QpZpeb.jpg)
- 黑苹果安装不识别SATA硬盘
  - 15.7含之前请用SATA-unsupported.kext
  - 11.0含之后请用CtlnaAHCIPort.kext
> 下载链接：https://pan.bilnn.com/s/ggryul
> 备用链接：https://shoaling.lanzoui.com/iJZRvmaeegb

- 请将驱动移动至
  - OC引导: **OC-kexts** 并编辑oc-config.plist配置表添加加载信息
  - 四叶草引导: "CLOVER-kexts-Other"无需编辑配置表直接移入重新引导即可



