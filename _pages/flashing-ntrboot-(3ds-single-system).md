---
title: "刷入ntrboot（3DS单系统）"
---

### 教程须知

开始之前，确保你已经完整阅读了[ntrboot](ntrboot)页面的信息。

本方法仅需你的未破解的3DS和一个兼容的烧录卡。本方法通过烧录卡运行一个刷入ntrboot的`.nds`文件。这意味着你的烧录卡必须支持在你的3DS上运行`.nds`文件。参见[ntrboot](ntrboot)页面的烧录卡列表了解更多信息。

在某些罕见的情况下，刷入操作可能会造成盗版烧录卡**变砖**，使其永远无法使用。仅原装的在表中列出的烧录卡支持ntrboot。为减少买到盗版烧录卡的几率，推荐你在一个有信誉的网站上购买烧录卡（例如[NDS Card](http://www.nds-card.com/)）。（译者注：国内渠道较多，淘宝上建议选销量较大的商家，或者烧录卡官网链接的网店）。
{: .notice--danger}

### 你需要

* 和ntrboot兼容的烧录卡
* 最新版本的[ds_ntrboot_flasher](https://github.com/ntrteam/ds_ntrboot_flasher/releases/latest){:target="_blank"} *（`dsi`烧录器，不是标准烧录器）*

### 操作指南

#### 第一部分 - 准备工作

1. 关机
1. 将烧录卡的SD卡插入电脑
1. 将`ds_ntrboot_flasher_dsi.nds`文件拷贝到烧录卡的SD卡中
1. 将烧录卡的SD卡插回烧录卡
1. 将烧录卡插入机器

#### 第二部分 - 刷入ntrboot

1. 在机器上通过烧录卡运行`ds_ntrboot_flasher_dsi.nds`
1. 按(A)键继续
1. 用(Up)和(Down)键选择你的烧录卡
1. 按(A)键继续
1. 按(A)键"inject ntrboothax"
1. 按(A)键选择“RETAIL”
1. 按(A)键继续
1. 选择“EXIT”

___

### 继续进入[安装boot9strap（ntrboot）](installing-boot9strap-(ntrboot))
{: .notice--primary}
