---
title: "安装arm9loaderhax"
permalink: /installing-arm9loaderhax.html
lang: zh_CN
ref: installing-arm9loaderhax
---

本教程的最后一步是安装arm9loaderhax和Luma3DS，以便启动机器的数毫秒内就能进入CFW。这要用到[AuroraWright](https://github.com/AuroraWright/)编写的SafeA9LHInstaller。
{: .notice}

这将安装[AuroraWright版](https://github.com/AuroraWright/arm9loaderhax)arm9loaderhax.
{: .notice--info}

我们还会配置通过arm9loaderhax启动小程序（payloads）的能力，使我们能通过恢复备份，将通常情况下变砖的设备解砖。
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
+  **Hourglass9** *(可以进行NAND和卡带操作的多功能工具)*

#### 你需要

* <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [`aeskeydb.bin`](magnet:?xt=urn:btih:18b3a17f78e2376e05feaa150749d9fd689b25dc&dn=aeskeydb.bin&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [`fbi-2.4.2-injectable.zip`](magnet:?xt=urn:btih:f978b4cf5eda72823240b9c649f3fd2940a9f525&dn=fbi-2.4.2-injectable.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [`data_input_v3.zip`](magnet:?xt=urn:btih:a1195c9f7ab650fa7c7bf020b51fc19ea8d9440c&dn=data%5Finput%5Fv3.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* 最新改版的[SafeA9LHInstaller](https://github.com/Plailect/SafeA9LHInstaller/releases/latest) *（`.7z`压缩包）*
* 最新版的[arm9loaderhax](https://github.com/AuroraWright/arm9loaderhax/releases/latest) *（`.7z`压缩包）*
* 最新版的[Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *（`.7z`压缩包）*
* 最新版的[hblauncher_loader](https://github.com/yellows8/hblauncher_loader/releases/latest)
* 最新版的[Hourglass9](https://github.com/d0k3/Hourglass9/releases/latest)
* 最新版的[Luma3DS Updater](https://github.com/Hamcha/lumaupdate/releases/latest)
* 最新版的[DspDump](https://github.com/Cruel/DspDump/releases/latest)
* 最新版的[FBI](https://github.com/Steveice10/FBI/releases/latest)
* 自制程序[新手包](http://smealum.github.io/ninjhax2/starter.zip)

#### 操作指南

##### 第一部分 - 准备工作

{% capture notice-5 %}
**确保你使用的SD卡没有损坏！**

**如果你使用了一个损坏的SD卡，你的设备可能变砖！**

**如果你认为你的SD卡可能损坏，可以使用如下工具进行检测：[H2testw (Windows)](h2testw-(windows))，[F3 (Linux)](f3-(linux))，[F3X (Mac)](f3x-(mac))**
{% endcapture %}

<div class="notice--danger">{{ notice-5 | markdownify }}</div>

1. **如果你SD卡上已经存在`/files9/`目录，请复制该文件夹到你电脑上一个安全的地方，并在多个位置进行备份（如网盘）；当发生系统崩溃时，这里面的文件可以防止你丢失所有的数据**
2. 在你的SD卡上创建一个名为`cias`的文件夹（如果不存在的话）
3. 删除SD卡的`3ds`文件夹，如果存在的话
5. 解压`starter.zip`压缩包，并复制`starter`文件夹下的所有文件到你SD卡的根目录
   + 这里面包括一个新的`3ds`文件夹，替换你刚刚删除的`3ds`文件夹
6. 解压SafeA9LHInstaller`.7z`压缩包，并复制_解压后的文件_到你SD卡的根目录
7. 解压data_input`.zip`压缩包，并复制`a9lh`文件夹到SD卡的根目录
8. 解压arm9loaderhax`.7z`压缩包，并复制_解压后的文件_到SD卡的`a9lh`目录下
9. 解压hblauncher\_loader`.zip`压缩包，并复制`hblauncher_loader.cia`文件到SD卡的`/cias/`目录下
10. 解压Luma3DS Updater压缩包，并复制 `lumaupdater.cia` 到SD卡的`/cias/`目录下
11. 解压FBI压缩包，并复制`FBI.cia` 到SD卡的`/cias/`目录下
12. 解压Luma3DS压缩包，复制`arm9loaderhax.bin`文件到你SD卡的根目录，覆盖已有的文件
13. 在SD卡根目录下，创建名为`luma`的文件夹
14. 在SD卡的`luma`文件夹里，创建名为`payloads`的文件夹
15. 解压Hourglass9`.zip`压缩包，复制`Hourglass9.bin`文件到SD卡的`/luma/payloads/`目录下，并重命名`Hourglass9.bin`为 `start_Hourglass9.bin`
17. 复制`aeskeydb.bin`文件到SD卡的`/files9/`目录下
18. 复制`DspDump.3dsx`文件到SD卡的`/3ds/`目录下
19. 解压缩`fbi-2.4.2-injectable.zip`压缩包，并复制_解压后的文件_到SD卡的`/files9/`目录下

##### 第二部分 - 安装 arm9loaderhax

1. 将SD卡插回你的3DS
2. 按照如下步骤安装arm9loaderhax：
  + 你的系统版本应该在2.1.0
  + 在3DS的浏览器里打开`http://2xrsa.3ds.guide`网址
   + 如果出现错误：“当前服务在你的区域不可用”，请使用系统设置修改你的设备所在的国家，匹配你安装的2.1.0 ctr转移镜像所对应的NAND区域
   + 如果出现错误，[参见这个问题排查](troubleshooting#ts_browser)
   + 如果出现花屏，[参见这个问题排查](troubleshooting#ts_safe_a9lh_screen)
   + 如果你的设备是2DS或新3DS，且没有打开wifi，可以断开充电器并取下电池等几秒钟，即可重新开启wifi
  + 按(Select)键，进行完整安装（Full Install）
  + 安装程序将在你的设备上安装arm9loaderhax（速度很快）
  + 按任意键关机
  + 复制SD卡`/a9lh/`目录下你设备专属的`otp.bin`文件到你电脑上一个安全的地方，并在多个位置进行备份（如网盘），然后将SD卡插回3DS上

##### 第三部分 - 设置 Luma3DS

1. 按住(Select)键并开机，进入Luma3DS的菜单
  + 请确保按电源键之前就按住(select)键
  + 如果黑屏，[参见这个问题排查](troubleshooting#ts_sys_a9lh)
  + 如果你进入了SafeA9LHInstaller，[参见这个问题排查](troubleshooting#ts_safe_a9lh)
2. 通过方向键和A键来启用以下设置：
  + **"Autoboot SysNAND"**
  + **"Use SysNAND FIRM if booting with R"**
  + **"Show NAND or user string in System Settings"**
3. 如果你的设备是**新3DS**，你*还*可以启用如下设置：
  + **"New 3DS CPU"选项，请移动光标到"Clock+L2(x)"**
   + 这将提升许多游戏的帧率，但可能会造成某些游戏的不稳定
   + 如果有部分游戏不能正常运行，关闭这个选项并重试
4. 按下(Start)键保存设置并重启
  + 如果出现黑屏，请照常进行接下来的教程
  + 如果出现"Failed to mount CTRNAND"错误，请照常进行接下来的教程

##### 第四部分 - 恢复系统

如果在进行本教程之前，你已经安装了EmuNAND，并且想将之前EmuNAND中的数据迁移到新的SysNAND自制系统中，请在开始本部分操作之前先按照[迁移EmuNAND数据](move-emunand)一节进行，然后跳过本部分的前四步。
{: .notice--info}

1. 按住(Start)键并开机，通过arm9loaderhax进入Hourglass9
2. 选择"SysNAND Backup/Restore"
3. 选择"SysNAND Restore (keep a9lh)"，从`NANDmin.bin`文件中恢复原系统的备份文件
4. 按(Start)键重启
  + 如果出现黑屏，参见[9.2.0 ctr转移](9.2.0-ctrtransfer)
5. 如果你的备份文件系统版本在3.0.0到4.5.0，除非你下载所需的固件，否则你的设备将无法开机：
  + 下载[这个文件](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000056)并重命名为`firmware.bin`
  + 下载[这个文件](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk)
  + 复制`firmware.bin`和`cetk`这两个文件到SD卡的`/luma/`目录下
  + 在你的3DS升级完成后，删除这两个文件
6. 进入"System Settings"（系统设置）、"Other Settings"（其它设置），移动到最右边一页，选择"System Update"（系统升级），将你的3DS系统升级到最新版本
  + 使用A9LH + Luma（或者其它自制系统）进行系统升级很安全，请不要再问这个问题。
  + 之前关于新3DS不能在2.1.0系统版本下进行升级的警告不适用于恢复了你的NAND备份之后（译者注：因为已经不是2.1.0系统了）
  + 如果出现错误，将你的DNS设置改为"auto"（自动）模式
  + 如果仍然出现错误，并且你的固件版本在9.2.0以下，参见[9.2.0 ctr转移](9.2.0-ctrtransfer)


##### 第五部分 - 注入FBI

1. 按住(Start)键并开机，通过arm9loaderhax进入Hourglass9
2. 选择"SysNAND Backup/Restore"，然后选择"Health&Safety Dump"，导出健康与安全（Health & Safety）应用到`hs.app`文件**（你可以通过十字键上下/左右来修改导出的文件名）**
3. 按(B)键，选择"Health&Safety Inject"
4. 依照你的设备区域，选择可以注入的FBI`.app`文件
5. 按(A)键确认，进行注入
6. 按(Start)键重启
7. 如果你依然进入的是系统内置的Health & Safety应用，并且之前曾经用Gateway进行过降级，参见这个[问题排查](troubleshooting#gw_fbi)

##### 第六部分 - 最终设置

1. 打开健康与安全（Health & Safety）应用（现在应该是FBI）
2. 选择"SD"
3. 选择"cias"
4. 选择`FBI.cia`文件，按(A)键安装
5. 选择`hblauncher_loader.cia`文件，按(A)键安装
6. 选择`lumaupdater.cia`文件，按(A)键安装
7. 按(B)键返回SD卡目录
8. 选择`arm9loaderhax.bin`文件，按(A)键并选择`copy`（复制）选项
9. 按(B)键返回FBI主菜单
10. 选择"CTR NAND"
11. 选择"\<current directory>"
12. 选择`Paste`（粘贴）选项，并按(A)键确认
13. 按(Home)键退出
14. 从桌面菜单中运行自制程序启动器（Homebrew Launcher）
15. 选择"DSP Dump"
16. 依照提示，按(Start)键退出
17. 按住(Start)键并开机，进入Hourglass9
18. 选择"SysNAND Backup/Restore"，然后选择"Health&Safety Inject"
19. 选择`hs.app`文件(原来不包含FBI的版本)，然后按(A)键确认注入
20. 在主菜单中，按(Select)键弹出你的SD卡
21. 按(Start)键，在没有SD卡的情况下重启
  + 在没有SD卡的情况下至少开启一次你的机器，可以使你配置基于CTRNAND的Luma3DS
22. 使用方向键和(A)键来启用以下设置：
  + **"Show NAND or user string in System Settings"**
23. 如果你的设备是**新3DS**，你*还*可以启用如下设置：
  + **"New 3DS CPU"选项，请移动光标到"Clock+L2(x)"**
    + 这将提升许多游戏的帧率，但可能会造成某些游戏的不稳定
    + 如果有部分游戏不能正常运行，关闭这个选项并重试
24. 将SD卡插回3DS，按下(Start)键保存设置并重启！

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
现在你将默认启动到一个自制的SysNAND系统。
你可以在启动时按下(Select)键，进入Luma3DS的设置菜单。
你可以在启动时按下(Start)键，运行Hourglass9。
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>

如果你以后想升级你的arm9loaderhax，请参见[升级A9LH](updating-a9lh)页面。
{: .notice--info}

如果要使用[NTR CFW](https://github.com/44670/BootNTR/)，从[这里](https://github.com/44670/BootNTR/releases)选择合适的zip压缩包并提取`ntr.bin`文件，把这个文件复制到你SD卡的根目录下，然后从[这里](https://github.com/astronautlevel2/BootNTR/releases/latest)下载安装`BootNTR.cia`。
{: .notice--info}

保留好你的`NANDmin.bin`文件，以便以后使用Hourglass9恢复NAND救砖。
{: .notice--info}

只要你在其他安全的地方有备份，你就可以从`/files9/`文件夹删除NAND备份文件。
{: .notice--info}

{% capture notice-7 %}
**你可以将下表中没有的文件和文件夹从SD卡中删除：**

 + 3ds
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
