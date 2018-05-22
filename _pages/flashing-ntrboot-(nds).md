---
title: "刷入ntrboot（NDS）"
---

### 教程须知

开始之前，确保你已经完整阅读了[ntrboot](ntrboot)页面的信息。

本方法需要临时用到一台与你的烧录卡兼容的Nintendo DS或Nintendo DS Lite机器。

在某些罕见的情况下，刷入操作可能会造成盗版烧录卡**变砖**，使其永远无法使用。仅原装的在表中列出的烧录卡支持ntrboot。为减少买到盗版烧录卡的几率，推荐你在一个有信誉的网站上购买烧录卡（例如[NDS Card](http://www.nds-card.com/)）。（译者注：国内渠道较多，淘宝上建议选销量较大的商家，或者烧录卡官网链接的网店）。
{: .notice--danger}

### 你需要

* 和ntrboot兼容的烧录卡
* 两台机器
  + **来源NDS / NDSL**：与你的烧录卡兼容的Nintendo DS或Nintendo DS Lite
  + **目标3DS**：未破解的机器
* 最新版本的[ds_ntrboot_flasher](https://github.com/ntrteam/ds_ntrboot_flasher/releases/latest){:target="_blank"} *（标准烧录器，不是`dsi`烧录器）*

### 操作指南

#### 第一部分 - 准备工作

1. 关闭**来源NDS / NDSL**
1. 将烧录卡的SD卡插入电脑
1. 将`ds_ntrboot_flasher.nds`文件拷贝到烧录卡的SD卡中
1. 将烧录卡的SD卡插回烧录卡
1. 将烧录卡插入机器**来源NDS / NDSL**

#### 第二部分 - 刷入ntrboot

1. 在**来源DSi**上通过烧录卡运行`ds_ntrboot_flasher.nds`
1. 按(A)键继续
1. 用(Up)和(Down)键选择你的烧录卡
1. 按(A)键继续
1. 按(X)键"load flashrom"
1. 按(A)键继续
1. 从**来源NDS / NDSL**上弹出烧录卡
1. 从烧录卡上取下SD卡
1. 将移除SD卡的烧录卡插回**来源NDS / NDSL**
1. 按(A)键继续
1. 按(A)键"inject ntrboothax"
1. 按(A)键选择“RETAIL”
1. 从**来源NDS / NDSL**上弹出烧录卡

___

### 继续进入[安装boot9strap（ntrboot）](installing-boot9strap-(ntrboot))
{: .notice--primary}
