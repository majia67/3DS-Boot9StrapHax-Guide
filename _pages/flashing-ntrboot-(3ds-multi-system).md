---
title: "刷入ntrboot（3DS多系统）"
---

### 教程须知

开始之前，确保你已经完整阅读了[ntrboot](ntrboot)页面的信息。

本方法需要用到另一个已经运行boot9strap的3DS家族机器。这对你的烧录卡支持的系统版本没有任何要求。参见[ntrboot](ntrboot)页面的烧录卡列表了解更多信息。

在某些罕见的情况下，刷入操作可能会造成盗版烧录卡**变砖**，使其永远无法使用。仅原装的在表中列出的烧录卡支持ntrboot。为减少买到盗版烧录卡的几率，推荐你在一个有信誉的网站上购买烧录卡（例如[NDS Card](http://www.nds-card.com/)）。（译者注：国内渠道较多，淘宝上建议选销量较大的商家，或者烧录卡官网链接的网店）。
{: .notice--danger}

### 你需要

* 和ntrboot兼容的烧录卡
* 两台3DS家族的机器
  + **来源3DS**：已经运行boot9strap的3DS家族机器
  + **目标3DS**：未破解的机器
* 最新版本的[boot9strap](https://github.com/SciresM/boot9strap/releases/latest){:target="_blank"} *（`ntr`版boot9strap；不是`devkit`版）*
* 最新版本的[ntrboot_flasher](https://github.com/ntrteam/ntrboot_flasher/releases/latest){:target="_blank"}

### 操作指南

#### 第一部分 - 准备工作

1. 关闭**来源3DS**
1. 将**来源3DS**的SD卡插入电脑
1. 在SD卡根目录创建名为`ntrboot`的文件夹
1. 解压缩boot9strap ntr `.zip`压缩包，复制`boot9strap_ntr.firm`和`boot9strap_ntr.firm.sha`文件到SD卡的`/ntrboot/`文件夹下
1. 复制`ntrboot_flasher.firm`文件到SD卡的`/luma/payloads/`文件夹下
1. 将SD卡插回**来源3DS**
1. 将ntrboot兼容的DS / DSi烧录卡插入**来源3DS**

#### 第二部分 - 刷入ntrboot

1. 在**来源3DS**开机时按住(Start)键，运行Luma3DS启动器
1. 选择"ntrboot_flasher"
1. 阅读屏幕上红色的警告文字
1. 按(A)键继续
1. 选择你的烧录卡
  + 如果你在列表顶端没有看到你的烧录卡，请阅读下屏中针对每个选项的提示信息
1. 选择"Dump Flash"
1. 等待操作完成
1. 按(A)键继续
1. 按(A)键返回到主菜单
1. 选择"Inject Ntrboot"
1. 按(A)键选择零售版ntrboot
1. 等待操作完成
1. 按(A)键返回到主菜单
1. 按(B)键关机

___

### 继续进入[安装boot9strap（ntrboot）](installing-boot9strap-(ntrboot))
{: .notice--primary}
