---
title: "安装Boot9Strap（系统设置）"
---

如果你的3DS之前已经破解，并安装了基于EmuNAND的自制系统，请务必注意本教程仅适用于SysNAND，教程内的步骤应当应用在你的SysNAND上。注意EmuNAND和RedNAND是[同一概念](http://3dbrew.org/wiki/NAND_Redirection)的两种略微不同的实现。
{: .notice--info}

#### 你需要

* 最新版的[SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* 最新版的[boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *（标准版boot9strap；不是`devkit`或`ntr`版）*
* 最新版的[Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *（`.7z`压缩包）*
* 自制程序[新手包](http://smealum.github.io/ninjhax2/starter.zip)
* 可以在你的3DS上正常工作的DS烧录卡

#### 操作指南

##### 第一部分 - 准备工作

1. 关机
1. 将SD卡插入电脑
1. 解压Luma3DS`.7z`压缩包，复制`boot.firm`文件到你SD卡的根目录
1. 解压缩`starter.zip`压缩包，复制*解压后的文件和文件夹*到SD卡的根目录下
1. 在SD卡根目录创建名为`boot9strap`的文件夹（如果没有的话）
1. 解压缩boot9strap `.zip`压缩包，复制`boot9strap.firm`和`boot9strap.firm.sha`文件到SD卡的`/boot9strap/`目录下
1. 解压缩SafeB9SInstaller `.zip`压缩包，复制`SafeB9SInstaller.dat`文件到你的SD卡根目录
1. 将SD卡重新插回机器
1. 复制`SafeB9SInstaller.nds`文件到你的DS烧录卡中
1. 开机

##### 第二部分 - 运行SafeB9SInstaller

1. 从机器中进入烧录卡
1. 在烧录卡中运行`SafeB9SInstaller.nds`
1. 选择对应你系统版本的选项
  + 4.X.X -> "4.x SafeB9SInstaller"
  + 6.X.X -> "6.x SafeB9SInstaller"
1. 重启，然后进入系统设置（System Settings）- “其它选项”（"Other Settings"）- “资料”（"Profile"）- "Nintendo DS Profile"（译者注：没错，就是传说中的414）
1. 如果漏洞利用成功，你将进入SafeB9SInstaller

##### 第三部分 - 安装boot9strap

1. 等待所有安全检查完成
1. 按照提示输入按键组合，安装boot9strap
1. 完成后，按(A)键重启机器

##### 第四部分 - 设置Luma3DS

1. 你的机器应该启动到了Luma3DS启动器菜单
  + 如果黑屏，[参见这个问题排查](troubleshooting#ts_sys_b9s)
1. 通过方向键和A键来启用以下设置：
  + **"Show NAND or user string in System Settings"**
1. 按下(Start)键保存设置并重启
  + 如果出现错误，请继续进行接下来的教程

___

继续进行[收尾工作](finalizing-setup)
{: .notice--primary}
