---
title: "安装Boot9Strap（自制程序启动器）"
---

如果你的3DS之前已经破解，并安装了基于EmuNAND的自制系统，请务必注意本教程仅适用于SysNAND，教程内的步骤应当应用在你的SysNAND上。注意EmuNAND和RedNAND是[同一概念](http://3dbrew.org/wiki/NAND_Redirection)的两种略微不同的实现。
{: .notice--info}

#### 你需要

* 最新版的[SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* 最新版的[boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *（标准版boot9strap；不是`devkit`或`ntr`版）*
* 最新版的[safehax](https://github.com/TiniVi/safehax/releases/)
* 最新版的[udsploit](https://github.com/smealum/udsploit/releases/latest)
* 最新版的[Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *（`.7z`压缩包）*

#### 操作指南

##### 第一部分 - 准备工作

1. 将SD卡从机器中取出，将机器停留在自制程序启动器界面，然后将SD卡插入电脑
1. 解压Luma3DS`.7z`压缩包，复制`boot.firm`文件到你SD卡的根目录
1. 在SD卡根目录下创建`boot9strap`文件夹（如果没有的话）
1. 解压缩boot9strap `.zip`压缩包，复制`boot9strap.firm`和`boot9strap.firm.sha`文件到SD卡的`/boot9strap/`目录下
1. 复制`safehax.3dsx`文件到SD卡的`/3ds/`目录下
1. 复制`udsploit.3dsx`文件到SD卡的`/3ds/`目录下
1. 解压缩SafeB9SInstaller `.zip`压缩包，复制`SafeB9SInstaller.bin`文件到SD卡根目录，并重命名为`safehaxpayload.bin`

    ![]({{ base_path }}/images/screenshots/boot9strap-hb-file-layout.png)
    {: .notice--info}

1. 将SD卡重新插回机器

##### 第二部分 - 运行SafeB9SInstaller

1. 从自制程序列表中选择udsploit运行
  + 可能需要将列表往下拖才能看到这个选项
1. 运行结束后，按(Start)键退出udsploit
  + 可能需要多试几次
  + 如果画面卡死，长按电源键关机，然后再试一次
1. 从自制程序列表中选择safehax运行
  + 可能需要将列表往下拖才能看到这个选项
  + 如果出现"PM INIT FAILED"错误，确保你运行udsploit的时候开启了无线通讯（即Wifi）
  + 如果*还是*会出现"PM INIT FAILED"错误，尝试换用[r19版safehax](https://github.com/TiniVi/safehax/releases/tag/r19)
  + 如果画面卡死，长按电源键关机，然后再试一次
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
