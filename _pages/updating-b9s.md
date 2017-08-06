---
title: "升级B9S"
---

本节教程将帮助已经安装了boot9strap的用户升级boot9strap到最新版本。
{: .notice--info}

请注意，Luma3DS最近的更新与boot9strap 1.0版*不*兼容。你*需要*参照本节教程中的步骤升级你的boot9strap到1.2版。
{: .notice--warning}

{% capture notice-1 %}
我们收到一系列有关使用自制系统被任天堂封号的报告。为了保护你自己，请在开始本破解教程之前执行如下步骤：

1. 依次进入系统设置 -> "Internet Settings" （互联网设置） -> "SpotPass" -> "Sending of System Information"（发送系统信息）
1. 禁用"Sending of System Information"（发送系统信息）选项
1. 退出系统设置
1. 进入你的朋友列表（Home菜单上面一排图标中的笑脸图标）
  + 如果出现错误并退出了菜单，那么朋友列表设置已经被禁用了
1. 进入朋友列表设置 -> "Friend Notification Settings"（朋友通知设置） ->  "Show friends what you're playing"（告诉朋友们你在玩什么）
1. 禁用"Show friends what you're playing"（告诉朋友们你在玩什么）选项
1. 退出朋友列表

{% endcapture %}

<div class="notice--danger">{{ notice-1 | markdownify }}</div>

#### 你需要

* 最新版的[Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *（`.7z`压缩包）*
* 最新版的[SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* 最新版的[boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *（标准boot9strap；不是`devkit`或`ntr`版）*
* 最新版的[GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* 自制程序[新手包](http://smealum.github.io/ninjhax2/starter.zip)
* [`setup_ctrnand_luma3ds.gm9`]({{ base_path }}/gm9_scripts/setup_ctrnand_luma3ds.gm9)

#### 操作指南

##### 第一部分 - 准备工作

本部分中，复制任何文件到SD卡时，如果SD卡上已有该文件，请选择覆盖。
{: .notice--info}

1. 关机
1. 将SD卡插入电脑
1. **保留旧版本（v7.1）的Luma3DS（`boot.firm`文件）。之后会升级它。**
1. 解压缩`starter.zip`压缩包，复制*解压后的文件和文件夹*到SD卡的根目录
1. 在SD卡根目录创建`boot9strap`文件夹
1. 解压`GodMode9`压缩包，复制`GodMode9.firm`文件（arm9loaderhax用户请使用`GodMode9.bin`文件）到SD卡的`/luma/payloads/`目录下，复制`gm9`文件夹到SD卡根目录下
1. 复制`setup_ctrnand_luma3ds.gm9`文件到SD卡的`/gm9/scripts/`目录下
1. 解压缩SafeB9SInstaller`.zip`压缩包，复制`SafeB9SInstaller.firm`文件到SD卡的`/luma/payloads/`目录下
1. 解压缩boot9strap`.zip`压缩包，复制`boot9strap.firm`和`boot9strap.firm.sha`文件到SD卡的`/boot9strap/`目录下
1. 将SD卡插回机器

##### 第二部分 - 安装boot9strap

1. 按住(Start)键开机，进入Luma3DS启动器菜单
1. 按(A)键运行SafeB9SInstaller
1. 等待所有安全检查完成
1. 按照提示输入按键组合，安装boot9strap
1. 完成后，按(A)键重启机器
1. 关机
  + 请注意，在完成接下来的步骤之前，你会看到`Unsupported launcher (argc = 0)`错误

##### 第三部分 - 升级Luma3DS

1. 将SD卡插入电脑
1. 删除SD卡上已有的`boot.firm`文件
1. 解压缩Luma3DS`.7z`压缩包，复制`boot.firm`文件到SD卡根目录
1. 将SD卡插回机器

##### 第四部分 - 设置Luma3DS

1. 你的机器应该启动到了Luma3DS启动器菜单
  + 如果黑屏，[参见这个问题排查](troubleshooting#ts_sys_b9s)
1. 通过方向键和A键来启用以下设置：
  + **"Show NAND or user string in System Settings"**
1. 按下(Start)键保存设置并重启

##### 第五部分 - CTRNAND Luma3DS

1. 关机，按住(Start)键开机，运行GodMode9
1. 如果提示你创建文件备份，按(A)键执行，然后按(A)键继续教程
1. 按(Home)键打开行动菜单
1. 选择"More..."（更多）
1. 选择"Scripts..."（脚本）
1. 选择"setup_ctrnand_luma3ds"
1. 出现提示时，按(A)键继续
1. 按(A)键解锁SysNAND (lvl1)写保护，然后输入提示的按键组合
1. 按(A)键继续
1. 按(A)键重新加上写保护
1. 按(Start)键重启

___

注意`/boot9strap/`目录下的`.bak`文件仅在安装boot9strap失败的时候有用。在你安装成功后，你可以删除整个`boot9strap`文件夹。
{: .notice--info}

你可以在系统启动时按下(L) + (Down) + (Select)键，打开Luma3DS内置的Rosalina菜单。如果想了解Rosalina的全部特性，参见[Luma3DS v8.0 Release](https://github.com/AuroraWright/Luma3DS/releases/tag/v8.0)。
{: .notice--info}