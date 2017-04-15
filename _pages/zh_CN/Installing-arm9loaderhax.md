---
title: "安装arm9loaderhax"
permalink: /installing-arm9loaderhax.html
---

本教程的最后一步是安装arm9loaderhax和Luma3DS，以便启动机器的数毫秒内就能进入CFW。这要用到[AuroraWright](https://github.com/AuroraWright/)编写的SafeA9LHInstaller。
{: .notice}

这将安装[AuroraWright版](https://github.com/AuroraWright/arm9loaderhax)arm9loaderhax.
{: .notice--info}

我们还会配置通过arm9loaderhax启动小程序（payloads）的能力，使我们能通过恢复备份，将通常情况下变砖的设备解砖。
{: .notice--info}

你需要一个能进行BT下载的软件，如[Deluge](http://dev.deluge-torrent.org/wiki/Download)、[aria2](https://aria2.github.io/)或迅雷，才能下载本节教程中的[磁力链接](http://baike.baidu.com/item/%E7%A3%81%E5%8A%9B%E9%93%BE%E6%8E%A5)。
{: .notice--info}

**请不要使用其它设备的OTP，否则你的设备一定会变砖！**
{: .notice--danger}

#### 步骤概览

本节我们将完成之前所有工作的最终目的：安装arm9loaderhax。

这几乎是所有设备破解中最好的一种，因为它能被永久安装到NAND固件分区中，并在大多数系统文件启动前运行，使得它不仅可以在*任何*版本上生效，而且能保护其自身，并可以从大多数使非A9LH破解的3DS变砖的情况恢复，如损坏的桌面菜单（home menu）或者安装了一个错误的title（条目，如系统文件、游戏、软件等等）。

在加载完NAND之后，arm9loaderhax会启动`arm9loaderhax.bin`文件，它可以是任何有效的arm9 payload。你可以随时替换该文件，尽管可以通过Luma3DS启动其它的arm9 payloads。

本教程中，我们使用[AuroraWright](https://github.com/AuroraWright/)编写的Luma3DS来直接启动一个破解过的SysNAND，使我们能完全避免使用EmuNAND，从而极大地简化使用破解3DS系统的方式，并节省SD卡的空间。

当我们安装完arm9loaderhax，并正确配置了Luma3DS之后，我们会将之前的备份恢复。

在这个过程当中，我们还会安装以下几种程序：
+  **FBI** *(安装CIA格式的游戏和应用)*
+  **Luma3DS Updater** *(轻松升级你安装的CFW)*
+  **GodMode9** *(可以进行NAND和卡带操作的多功能工具)*

#### 你需要

* <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [`aeskeydb.bin`](magnet:?xt=urn:btih:18b3a17f78e2376e05feaa150749d9fd689b25dc&dn=aeskeydb.bin&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [`data_input_v3.zip`](magnet:?xt=urn:btih:a1195c9f7ab650fa7c7bf020b51fc19ea8d9440c&dn=data%5Finput%5Fv3.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* 最新版的[SafeA9LHInstaller](https://github.com/Plailect/SafeA9LHInstaller/releases/latest) *（`.7z`压缩包）*
* 最新版的[arm9loaderhax](https://github.com/AuroraWright/arm9loaderhax/releases/latest) *（`.7z`压缩包）*
* 最新版的[Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *（`.7z`压缩包）*
* 最新版的[hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases/latest)
* 最新版的[GodMode9](https://github.com/d0k3/GodMode9/releases/)
* 最新版的[Luma3DS Updater](https://github.com/Hamcha/lumaupdate/releases/latest)
* 最新版的[FBI](https://github.com/Steveice10/FBI/releases/latest)

#### 操作指南

##### 第一部分 - 准备工作

1. 将SD卡插入电脑
1. **如果在`/ctrtransfer/`文件夹中存在`<serialnumber>_nand.bin`文件（serialnumber是你的设备的序列号），将其复制到你的电脑上一个安全的位置
  + 在多个位置进行备份（如网盘）
  + 当发生系统崩溃时，这里面的文件可以防止你的设备变砖
1. 在SD卡上创建一个名为`cias`的文件夹（如果不存在的话）
1. 在SD卡上创建一个名为`files9`的文件夹（如果不存在的话）
1. 解压SafeA9LHInstaller`.7z`压缩包，并复制*解压后的文件*到你SD卡的根目录
1. 解压data_input`.zip`压缩包，并复制`a9lh`文件夹到SD卡的根目录
1. 解压arm9loaderhax`.7z`压缩包，并复制*解压后的文件*到SD卡的`a9lh`目录下
1. 解压hblauncher\_loader`.zip`压缩包，并复制`hblauncher_loader.cia`文件到SD卡的`/cias/`目录下
1. 解压Luma3DS Updater压缩包，并复制 `lumaupdater.cia` 到SD卡的`/cias/`目录下
1. 解压FBI压缩包，并复制`FBI.cia` 到SD卡的`/cias/`目录下
1. 解压Luma3DS压缩包，复制`arm9loaderhax.bin`文件到你SD卡的根目录，覆盖已有的文件
1. 在SD卡根目录下，创建名为`luma`的文件夹
1. 在SD卡的`luma`文件夹里，创建名为`payloads`的文件夹
1. 解压GodMode9`.zip`压缩包，复制`GodMode9.bin`文件到SD卡的`/luma/payloads/`目录下，并将其重命名为`start_GodMode9.bin`
1. 复制`aeskeydb.bin`文件到SD卡的`/files9/`目录下

##### 第二部分 - 安装 arm9loaderhax

1. 将SD卡插回你的机器
1. 你的系统版本应该是2.1.0，并且已经开机
1. 在3DS的浏览器里打开网址：`http://2xrsa.3ds.guide`
  + 如果出现错误：“当前服务在你的区域不可用”，请使用系统设置修改你的设备所在的国家，匹配你安装的2.1.0 ctr转移镜像所对应的NAND区域
  + 如果出现错误，[参见这个问题排查](troubleshooting#ts_browser)
  + 如果出现花屏，[参见这个问题排查](troubleshooting#ts_safe_a9lh_screen)
  + 如果你的设备是2DS或新3DS，且没有打开wifi，可以断开充电器并取下电池等几秒钟，即可重新开启wifi
1. 按(Select)键，进行完整安装（Full Install）
1. 安装程序将在你的设备上安装arm9loaderhax（速度很快）
1. 按任意键关机
1. 复制SD卡`/a9lh/`目录下你设备专属的`otp.bin`文件到你电脑上一个安全的地方，并在多个位置进行备份（如网盘）
1. 将SD卡插回机器上

##### 第三部分 - 设置 Luma3DS

1. 按住(Select)键并开机，进入Luma3DS的菜单
  + 请确保按电源键之前就按住(select)键
  + 如果黑屏，[参见这个问题排查](troubleshooting#ts_sys_a9lh)
  + 如果你进入了SafeA9LHInstaller，[参见这个问题排查](troubleshooting#ts_safe_a9lh)
1. 通过方向键和A键来启用以下设置：
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R"**
  + **"Show NAND or user string in System Settings"**
1. 按下(Start)键保存设置并重启
  + 如果出现黑屏，请照常进行接下来的教程
  + 如果出现"Failed to mount CTRNAND"错误，请照常进行接下来的教程

##### 第四部分 - 恢复系统 

如果在进行本教程之前，你已经安装了EmuNAND，并且想将之前EmuNAND中的数据迁移到新的SysNAND自制系统中，请在开始本部分操作之前先按照[迁移EmuNAND数据](move-emunand)一节进行，然后跳过本部分的前五步。
{: .notice--info}

1. 按住(Start)键开机，进入GodMode9
1. 进入`SDCARD` -> `ctrtransfer`
1. 选中`<serialnumber>_nand.bin`（serialnumber是你的设备的序列号）文件，按(A)键并选择"NAND image options..."（NAND镜像选项），然后选择"Restore SysNAND (safe)"
1. 按(A)键解锁SysNAND写保护，然后按照提示输入按键组合
  + 这不会覆盖你安装的arm9loaderhax
1. 按照提示输入按键组合，解锁SysNAND(lvl1)写保护
  + 该过程可能需要较长时间
1. 完成后，按(A)键继续
1. 按(Start)键重启
  + 如果出现黑屏，参见[9.2.0 ctr转移](9.2.0-ctrtransfer)
  + 现在新3DS可以安全地进入睡眠模式了
1. 如果你的备份文件系统版本在3.0.0到4.5.0，除非你下载所需的固件，否则你的机器将无法开机：
  + 下载[这个文件](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000056)并重命名为`firmware.bin`
  + 下载[这个文件](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk)
  + 复制`firmware.bin`和`cetk`这两个文件到SD卡的`/luma/`目录下
  + 在你的机器升级完成后，删除这两个文件
1. 进入"System Settings"（系统设置）、"Other Settings"（其它设置），移动到最右边一页，选择"System Update"（系统升级），将你的系统升级到最新版本
  + **请注意，因为11.4.0版本的系统最近刚发布，在上面运行Luma3DS还有一些bug（DS和GBA游戏无法运行）。并且NTR CFW还不与11.4.0版本的系统兼容。你可以先不升级系统，等新版的Luma3DS修复bug后再升级**
  + 使用A9LH + Luma（或者其它自制系统）进行系统升级很安全
  + 在你恢复了NAND备份后，之前关于新3DS不能在2.1.0系统版本下进行升级的警告就不再适用了（译者注：因为已经不是2.1.0系统了）
  + 如果出现错误，将你的DNS设置改为"auto"（自动）模式
  + 如果仍然出现错误，并且你的固件版本在9.2.0以下，参见[9.2.0 ctr转移](9.2.0-ctrtransfer)

##### 第五部分 - 注入FBI

1. 按住(Start)键重启，进入GodMode9
1. 进入`SDCARD` -> `files9`
1. 选中`FBI.cia`文件，按(A)键，并选择"CIA image options..."（CIA镜像选项），然后选择"Mount image to drive"（将镜像挂载到驱动器）
1. 选中`.app`文件，按(A)键，然后选择"NCCH image options"，并选择"Inject to H&S"
1. 按(A)键解锁SysNAND(lvl1)写保护，然后按照提示输入按键组合
1. 按(A)键继续
1. 按(Start)键重启
1. 如果你依然进入的是系统内置的健康与安全应用，并且之前曾经用Gateway进行过降级，参见这个[问题排查](troubleshooting#gw_fbi)

##### 第六部分 - 安装CIA文件

1. 在桌面菜单中运行健康与安全（Health & Safety）应用（现在应该是FBI）
1. 进入`SD` -> `cias`
1. 选择`\<current directory>`
1. 选择"Install all CIAs"（安装所有CIA文件）选项，按(A)键确认
1. 按(Home)键退出FBI

##### 第七部分 - 恢复“健康与安全”应用

1. 按住(Start)键重启，进入GodMode9
1. 按(Home)键打开菜单
1. 选择"More..."
1. 选择"Restore H&S"（恢复健康与安全应用）
1. 按(A)键解锁SysNAND(lvl1)写保护，然后按照提示输入按键组合

##### 第八部分 - CTRNAND Luma3DS

1. 进入`SDCARD`
1. 选中`arm9loaderhax.bin`文件，按(Y)键复制
1. 按(B)键返回到主菜单
1. 进入`SYSNAND CTRNAND`
1. 按(Y)键粘贴`arm9loaderhax.bin`文件
1. 选择"Copy path(s)"（复制路径）
1. 按(B)键返回到主菜单
1. 按住(R)键的同时按(B)键，弹出SD卡
1. 将SD卡从机器中取出
1. 按(Start)键，在没有SD卡的情况下重启
  + 在没有SD卡的情况下至少开启一次你的机器，可以使你配置基于CTRNAND的Luma3DS
1. 使用方向键和(A)键来启用以下设置：
  + **"Show NAND or user string in System Settings"**
1. 将SD卡插回3DS
1. 按下(Start)键保存设置并重启

___

如果DSi / DS 功能不能用了(比如DS卡带或者DSiWare无法工作), [参见这个问题排查](troubleshooting#twl_broken)
{: .notice--warning}

{% capture notice-10 %}
你现在可以使用Luma3DS Updater来更新你的Luma3DS到最新版，只需运行该程序并按下(A)键。
这和系统升级不是一回事；它只会下载并提取最新的Luma3DS文件。
这只会升级SD卡上的Luma3DS文件。如果你在没有SD卡的情况下开机，它会使用你放在CTRNAND上的版本。
{% endcapture %}

<div class="notice--info">{{ notice-10 | markdownify }}</div>

{% capture notice-6 %}
现在你将默认启动到Luma3DS自制SysNAND系统。
你可以在启动时按下(Select)键，进入Luma3DS的设置菜单。
你可以在启动时按下(Start)键，运行GodMode9。
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>

如果你以后想升级你的arm9loaderhax，请参见[升级A9LH](updating-a9lh)页面。
{: .notice--info}

保留好你的`<serialnumber>_nand.bin`（serialnumber是你的设备的序列号）文件，以便以后使用GodMode9恢复NAND救砖。
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

<div class="notice--info">{{ notice-7 | markdownify }}</div>

要想了解如何变更你的设备到另一个区域，参见[区域变更](region-changing)页面。
{: .notice--success}

要想了解如何升级你的arm9loaderhax，参见[升级A9LH](updating-a9lh)页面。
{: .notice--success}

要想了解如何使用Luma3DS的各种功能，参见[这个wiki](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage).
{: .notice--success}
