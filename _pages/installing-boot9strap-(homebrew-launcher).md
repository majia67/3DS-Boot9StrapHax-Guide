---
title: "安装Boot9Strap（自制程序启动器）"
---

如果你的3DS之前已经破解，并安装了基于EmuNAND的自制系统，请务必注意本教程仅适用于SysNAND，教程内的步骤应当应用在你的SysNAND上。注意EmuNAND和RedNAND是[同一概念](http://3dbrew.org/wiki/NAND_Redirection)的两种略微不同的实现。
{: .notice--info}

#### 操作指南

##### 第一部分 - 运行SafeB9SInstaller

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

##### 第二部分 - 安装boot9strap

1. 等待所有安全检查完成
1. 按照提示输入按键组合，安装boot9strap
1. 完成后，按(A)键重启机器

##### 第三部分 - 设置Luma3DS

1. 你的机器应该启动到了Luma3DS启动器菜单
  + 如果黑屏，[参见这个问题排查](troubleshooting#ts_sys_b9s)
1. 通过方向键和A键来启用以下设置：
  + **"Show NAND or user string in System Settings"**
1. 按下(Start)键保存设置并重启
  + 如果出现错误，请继续进行接下来的教程

___

继续进行[收尾工作](finalizing-setup)
{: .notice--primary}
