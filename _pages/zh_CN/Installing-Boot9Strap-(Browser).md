---
title: "安装Boot9Strap（浏览器）"
permalink: /installing-boot9strap-(browser).html
lang: zh_CN
---

如果你的3DS之前已经破解，并安装了基于EmuNAND的自制系统，请务必注意本教程仅适用于SysNAND，教程内的步骤应当应用在你的SysNAND上。注意EmuNAND和RedNAND是[同一概念](http://3dbrew.org/wiki/NAND_Redirection)的两种略微不同的实现。
{: .notice--info}

**你需要一个能进行BT下载的软件，如[Deluge](http://dev.deluge-torrent.org/wiki/Download)、[aria2](https://aria2.github.io/)或迅雷，才能下载本节教程中的[磁力链接](http://baike.baidu.com/item/%E7%A3%81%E5%8A%9B%E9%93%BE%E6%8E%A5)。**
{: .notice--info}

#### 你需要

* 最新版的[SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* 最新版的[boot9strap](https://github.com/SciresM/boot9strap/releases/latest)
* 自制程序[新手包](http://smealum.github.io/ninjhax2/starter.zip)

#### 操作指南

##### 第一部分 - 准备工作

1. 关机
1. 将SD卡插入电脑
1. 解压缩`starter.zip`压缩包，将*解压后的文件*拷贝到你SD卡的根目录，并将SD卡插回你的3DS
1. 在SD卡根目录创建一个名为`boot9strap`的文件夹
1. 解压缩boot9strap `.zip`压缩包，复制`boot9strap.firm`和`boot9strap.firm.sha`文件到SD卡的`/boot9strap/`目录下
1. 解压缩SafeB9SInstaller `.zip`压缩包，复制`SafeB9SInstaller.dat`文件到你的SD卡根目录
1. 将SD卡插回你的机器
1. 开机

#####　第二部分 - 运行SafeB9SInstaller

1. 打开浏览器，进入以下网址中的其中一个：
  + `https://dukesrg.github.io/?SafeB9SInstaller.dat`
  + 如果出现错误，参见[问题排查](troubleshooting#ts_browser)
1. 如果漏洞利用成功，SafeB9SInstaller将会启动

##### 第三部分 - 安装boot9strap

1. 等待所有安全检查完成
1. 按照提示输入按键组合，安装boot9strap
1. 完成后，按(A)键重启机器
1. 你的机器将启动到boot9strap，然后它会自动关机，因为还没有提供payload

___

继续进行[收尾工作](finalizing-setup)
{: .notice--primary}
