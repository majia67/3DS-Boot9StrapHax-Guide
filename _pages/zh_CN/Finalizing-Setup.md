---
title: "收尾工作"
permalink: /finalizing-setup.html
lang: zh_CN
---

**你需要一个能进行BT下载的软件，如[Deluge](http://dev.deluge-torrent.org/wiki/Download)、[aria2](https://aria2.github.io/)或迅雷，才能下载本节教程中的[磁力链接](http://baike.baidu.com/item/%E7%A3%81%E5%8A%9B%E9%93%BE%E6%8E%A5)。**
{: .notice--success}

#### 步骤概览

{% capture notice-2 %}

boot9strap完成加载NAND之后，会运行'boot.firm'文件。该文件可以是任何FIRM格式的arm9负载。你可以随时替换该文件，并且Luma3DS可以在启动器中运行其它arm9负载。
<br><br>
本教程中，我们使用[AuroraWright](https://github.com/AuroraWright/)编写的Luma3DS来直接启动一个破解过的SysNAND，使我们能完全避免使用EmuNAND，从而极大地简化使用破解3DS系统的方式，并节省SD卡的空间。
<br><br>
同时，我们还会安装以下几种程序：

+  **FBI** *(安装CIA格式的游戏和应用)*
+  **Themely** *(安装自制主题)*
+  **Luma3DS Updater** *(轻松升级你安装的CFW)*
+  **GodMode9** *(可以进行NAND和卡带操作的多功能工具)*

{% endcapture %}

<div class="notice--info">{{ notice-2 | markdownify }}</div>

#### 你需要

* 最新版的[Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *（`.7z`压缩包）*
+* 最新版的[Themely](https://github.com/ErmanSayin/Themely/releases/latest) *（`.cia` 文件）*
* 最新版的[hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases/latest)
* 最新版的[GodMode9](https://github.com/d0k3/GodMode9/releases/)
* 最新版的[DSP1](https://github.com/zoogie/DSP1/releases/latest)
* 最新版的[FBI](https://github.com/Steveice10/FBI/releases/latest)
* 最新版的[Luma3DS Updater](https://github.com/Hamcha/lumaupdate/releases/latest)
* **仅限老3DS和2DS：** 对应你的区域的老3DS 11.2.0-35 [otherapp负载](https://smealum.github.io/3ds/#otherapp)

#### 操作指南

##### 第一部分 - 准备工作

1. 将SD卡插入电脑
1. 在SD卡上创建一个名为`cias`的文件夹（如果不存在的话）
1. 在SD卡上创建一个名为`hblauncherloader`的文件夹（如果不存在的话）
1. 解压hblauncher\_loader`.zip`压缩包，并复制`hblauncher_loader.cia`文件到SD卡的`/cias/`目录下
1. 解压Luma3DS Updater压缩包，并复制 `lumaupdater-v2.0.cia` 到SD卡的`/cias/`目录下
1. 解压FBI压缩包，并复制`FBI.cia`文件到SD卡的`/cias/`目录下
1. 复制`DSP1.cia`文件到SD卡的`/cias/`目录下
1. 复制`Themely.cia`文件到SD卡的`/cias/`目录下

    ![]({{ base_path }}/images/screenshots/cias-file-layout.png)
    {: .notice--info}

1. 解压Luma3DS`.7z`压缩包，复制`boot.firm`文件到你SD卡的根目录，覆盖已有的文件
1. 在SD卡根目录下，创建名为`luma`的文件夹
1. 在SD卡的`luma`文件夹里，创建名为`payloads`的文件夹
1. 解压GodMode9`.zip`压缩包，复制`GodMode9.bin`文件到SD卡的`/luma/payloads/`目录下
1. **仅限老3DS和2DS：** 复制对应你的区域的老3DS 11.2.0-35 otherapp负载到SD卡的`/hblauncherloader/`目录下
1. **仅限老3DS和2DS：** 将刚才复制到SD卡的otherapp负载文件重命名为对应你的区域的名字：
  + **欧版：** `OLD-11-4-0-37-EUR.bin`
  + **日版：** `OLD-11-4-0-37-JPN.bin`
  + **韩版：** `OLD-11-4-0-37-KOR.bin`
  + **美版：** `OLD-11-4-0-37-USA.bin`

    ![]({{ base_path }}/images/screenshots/finalizing-setup-file-layout.png)
    {: .notice--info}

1. 如果你的备份文件系统版本在3.0.0到4.5.0，除非你下载所需的固件，否则你的机器将无法开机：
  + 下载[这个文件](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000056)并重命名为`firmware.bin`
  + 下载[这个文件](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk)
  + 复制`firmware.bin`和`cetk`这两个文件到SD卡的`/luma/`目录下
  + 在你的机器升级完成后，删除这两个文件
1. 将SD卡插回机器上

##### 第二部分 - 设置 Luma3DS

1. 按住(Select)键并开机，进入Luma3DS的菜单
  + 如果黑屏，[参见这个问题排查](troubleshooting#ts_sys_b9s)
1. 通过方向键和A键来启用以下设置：
  + **"Show NAND or user string in System Settings"**
1. 按下(Start)键保存设置并重启
  + 如果出现黑屏，请照常进行接下来的教程

##### 第三部分 - 升级系统

如果在进行本教程之前，你已经安装了EmuNAND，并且想将之前EmuNAND中的数据迁移到新的SysNAND自制系统中，请在开始本部分操作之前先按照[迁移EmuNAND数据](move-emunand)一节进行。
{: .notice--info}

1. 进入"System Settings"（系统设置）、"Other Settings"（其它设置），移动到最右边一页，选择"System Update"（系统升级），将你的系统升级到最新版本
  + 使用B9S + Luma（或者其它自制系统）进行系统升级很安全
  + 如果出现错误，将你的DNS设置改为"auto"（自动）模式
  + 如果仍然出现错误，并且你的固件版本在9.2.0以下，先进行[9.2.0 CTR转移](9.2.0-ctrtransfer)，然后尝试再次升级

##### 第四部分 - 注入FBI

1. 关机，按住(Start)键开机，进入Luma3DS启动器菜单
1. 按(A)键进入GodMode9
1. 进入`[0:] SDCARD` -> `cias`
1. 选中`FBI.cia`文件，按(A)键，并选择"CIA image options..."（CIA镜像选项），然后选择"Mount image to drive"（将镜像挂载到驱动器）
1. 选中`.app`文件，按(A)键，然后选择"NCCH image options"，并选择"Inject to H&S"
1. 按(A)键解锁SysNAND(lvl1)写保护，然后按照提示输入按键组合
1. 按(A)键继续
1. 按(Start)键重启
1. 如果你依然进入的是系统内置的健康与安全应用，并且之前曾经用Gateway进行过降级，参见这个[问题排查](troubleshooting#gw_fbi)

##### 第五部分 - 安装CIA文件

1. 在桌面菜单中运行健康与安全（Health & Safety）应用（现在应该是FBI）
1. 进入`SD` -> `cias`
1. 选择`\<current directory>`
1. 选择"Install all CIAs"（安装所有CIA文件）选项，按(A)键确认
1. 按(Home)键退出FBI

##### 第六部分 - 导出DSP

1. 运行DSP1
2. 导出完成后，按(Start)键退出

##### 第七部分 - 恢复“健康与安全”应用

1. 关机，按住(Start)键开机，进入Luma3DS启动器菜单
1. 按(A)键进入GodMode9
1. 按(Home)键打开菜单
1. 选择"More..."
1. 选择"Restore H&S"（恢复健康与安全应用）
1. 按(A)键解锁SysNAND(lvl1)写保护，然后按照提示输入按键组合

##### 第八部分 - CTRNAND Luma3DS

1. 关机，按住(Start)键开机，进入Luma3DS启动器菜单
1. 按(A)键进入GodMode9
1. 进入`[0:] SDCARD`
1. 选中`boot.firm`文件，按(Y)键复制
1. 按(B)键返回到主菜单
1. 进入`[1:] SYSNAND CTRNAND`
1. 按(Y)键粘贴`boot.firm`文件
1. 选择"Copy path(s)"（复制路径）
1. 按(A)键解锁SysNAND(lvl1)写保护，然后按照提示输入按键组合
1. 按(B)键返回到主菜单
1. 按住(R)键的同时按(B)键，弹出SD卡
1. 将SD卡从机器中取出
1. 按(Start)键，在没有SD卡的情况下重启
  + 在没有SD卡的情况下至少开启一次你的机器，可以使你配置基于CTRNAND的Luma3DS
1. 使用方向键和(A)键来启用以下设置：
  + **"Show NAND or user string in System Settings"**
1. 将SD卡插回机器
1. 按下(Start)键保存设置并重启

##### 第九部分 - 备份NAND

1. 关机，按住(Start)键开机，进入Luma3DS启动器菜单
1. 按(A)键进入GodMode9
1. 按(Home)键，打开行动菜单
1. 选择"More..."
1. 选择"Backup NAND"（备份系统）
1. 按(A)键继续
1. 按住(R)键的同时按(B)键，弹出SD卡
1. 将SD卡插入电脑
1. 复制`/gm9out`目录下的`nand.bin`文件到电脑上的一个安全的位置
  + 在备份文件复制到多个位置（比如网盘）
  + 如果以后系统出现问题，该备份文件可以防止你的机器变砖
1. 复制结束后，删除`/gm9out`目录下的`nand.bin`文件
1. 将SD卡插回机器
1. 按下(Start)键保存设置并重启

___

{% capture notice-10 %}
你现在可以使用Luma3DS Updater来更新你的Luma3DS到最新版，只需运行该程序并按下(A)键。
这和系统升级不是一回事；它只会下载并提取最新的Luma3DS文件。
这只会升级SD卡上的Luma3DS文件。如果你在没有SD卡的情况下开机，它会使用你放在CTRNAND上的版本。
{% endcapture %}

<div class="notice--info">{{ notice-10 | markdownify }}</div>

{% capture notice-6 %}
现在你将默认启动到Luma3DS自制SysNAND系统。
你可以按下(Select)键开机，进入Luma3DS的设置菜单。
你可以按下(Start)键开机，运行Luma启动器菜单（注意只有在Luma3DS检测到多于一个payload的时候才会显示菜单）。
你可以按下(Start) + (Select) + (X)键开机，导出ARM11 bootrom（`boot11.bin`），ARM9 bootrom（`boot9.bin`），以及你设备独有的OTP(`OTP.bin`)到SD卡的`/boot9strap`目录下（该过程没有任何提示信息）。
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>

如果你以后想升级你的arm9loaderhax，请参见[升级A9LH](updating-a9lh)页面。
{: .notice--info}

如果要使用[NTR CFW](https://github.com/44670/BootNTR/)，请安装[BootNTR Selector](https://gbatemp.net/threads/432911/)。
{: .notice--info}

{% capture notice-7 %}
**你可以将下表中没有的文件和文件夹从SD卡中删除：**

 + 3ds
 + DCIM
 + files9
 + hblauncherloader
 + luma
 + Nintendo 3DS
 + arm9loaderhax.bin
 + boot.3dsx

{% endcapture %}

{% capture notice-7 %}
将下图中**没有**列出的文件和文件夹从你的SD卡中删除：**
<br><br>
![]({{ base_path }}/images/screenshots/final-file-layout.png)
{% endcapture %}

<div class="notice--info">{{ notice-7 | markdownify }}</div>

要想了解如何变更你的设备到另一个区域，参见[区域变更](region-changing)页面。
{: .notice--success}

想了解如何使用GodMode9的各项功能，参见[GodMode9使用指南](godmode9-usage)页面。
{: .notice--success}

要想了解如何使用Luma3DS的各种功能，参见[这个wiki](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage)。
{: .notice--success}

要想了解如何安装自制主题、牌子和启动画面，参见[3dsthem.es](https://3dsthem.es/about.php)。
{: .notice--success}