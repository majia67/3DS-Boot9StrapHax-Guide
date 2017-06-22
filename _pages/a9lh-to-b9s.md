---
title: "从A9LH升级到B9S"
---

本节教程将帮助已安装了arm9loaderhax的用户升级到boot9strap。
{: .notice--info}

Luma3DS将来的所有版本将只以`.firm`格式发布，这意味着它将只和boot9strap和sighax兼容。这意味着如果想继续获得Luma3DS的最新更新，你需要通过本节教程升级你的自制系统。
{: .notice--info}

如果你的Luma3DS启用了PIN，SafeB9SInstaller会报出"OTP Crypto Fail"（OTP加密失败）的错误，除非你*要么*暂时禁用PIN（你可以在升级后重新启用PIN）*要么*下载下面的`aeskeydb.bin`文件。
{: .notice--warning}

你需要一个能进行BT下载的软件，如[Deluge](http://dev.deluge-torrent.org/wiki/Download)、[aria2](https://aria2.github.io/)或迅雷，才能下载本节教程中的[磁力链接](http://baike.baidu.com/item/%E7%A3%81%E5%8A%9B%E9%93%BE%E6%8E%A5)。
{: .notice--success}

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

下面名为`secret_sector.bin`的文件和之前教程中的多个版本的`data_input.zip`压缩包中包含的文件相同。如果你已经有了这个文件，就无需重新下载。
{: .notice--info}

新3DS需要`secret_sector.bin`文件来撤销arm9loaderhax破解，所以这不是安装boot9strap所必需的。如果你的机器不是新3DS，你就不需要`secret_sector.bin`文件。
{: .notice--info}

* **仅限新3DS：** <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [`secret_sector.bin`](magnet:?xt=urn:btih:15a3c97acf17d67af98ae8657cc66820cc58f655&dn=secret_sector.bin&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce)
* 最新版的[Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *（`.7z`压缩包）*
* 最新版的[SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* 最新版的[boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *（标准版boot9strap；不是`devkit`或`ntr`版）*
* 最新版的[GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* 最新改版的[Luma3DS Updater](https://github.com/KunoichiZ/lumaupdate/releases/latest)
* 自制程序[新手包](http://smealum.github.io/ninjhax2/starter.zip)

#### 操作指南

##### 第一部分 - 准备工作

本部分中，复制任何文件到SD卡时，如果SD卡上已有该文件，请选择覆盖。
{: .notice--info}

1. 关机
1. 将SD卡取下，插入电脑
1. 解压缩`starter.zip`压缩包，复制*解压后的文件和文件夹*到SD卡的根目录
1. 解压缩Luma3DS `.7z`压缩包，复制`boot.firm`文件到SD卡根目录
1. 在你的SD卡根目录创建名为`cias`的文件夹（如果不存在的话）
1. 复制`lumaupdater.cia`文件到SD卡的`/cias/`目录下
1. 在你的SD卡根目录创建名为`boot9strap`的文件夹
1. 解压缩GodMode9 `.zip`压缩包，复制`GodMode9.firm`文件到SD卡的`/luma/payloads/`目录下
1. 删除SD卡`/luma/payloads/`目录下的所有`.bin` payloads（负载文件），因为它们和boot9strap版的Luma3DS不兼容
1. 解压缩SafeB9SInstaller `.zip`压缩包，复制`SafeB9SInstaller.bin`文件到SD卡的`/luma/payloads/`目录下
1. 重命名SD卡`/luma/payloads/`目录下的`SafeB9SInstaller.bin`文件为`start_SafeB9SInstaller.bin`
1. 解压缩boot9strap `.zip`压缩包，复制`boot9strap.firm`和`boot9strap.firm.sha`文件到SD卡的`/boot9strap/`目录下
1. **仅限新3DS：**复制`secret_sector.bin`文件到SD卡的`/boot9strap/`目录下

    ![]({{ base_path }}/images/screenshots/a9lh-to-b9s-file-layout.png)
    {: .notice--info}

1. 将SD卡插回机器

##### 第二部分 - 安装boot9strap

1. 按住(Start)键开机，运行Luma3DS启动器菜单
  + 有些版本的Luma3DS会直接启动文件名前缀为`start_`的payload
  + 如果你的Luma3DS是这样的，跳过下一步
1. 按(A)键运行SafeB9SInstaller
  + 如果出现错误，尝试换用一张新的SD卡，或者格式化现有的SD卡（请先备份已有的文件）
1. 等待所有的安全检查完成
  + 如果出现错误"OTP Crypto Fail"（OTP加密失败），下载<i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [`aeskeydb.bin`](magnet:?xt=urn:btih:621f8af00638cb2b00d5bd0c6816543fa00b5fb1&dn=aeskeydb.bin&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce)文件，放到SD卡的`/boot9strap/`目录下，然后再试一次
1. 按照提示输入按键组合，安装boot9strap
1. 完成后，按(A)键重启机器
  + 如果你的机器开机后自动关机，确保你将Luma3DS `.7z`压缩包中的`boot.firm`文件复制到了SD卡的根目录下

##### 第三部分 - 设置 Luma3DS

本部分教程只有在重启后出现Luma3DS设置菜单时才需要执行。
{: .notice--info}

1. 通过方向键和A键来启用以下设置：
  + **"Show NAND or user string in System Settings"**
1. 按下(Start)键保存设置并重启

##### 第四部分 - CTRNAND Luma3DS

如果在进行本教程之前，你已经安装了EmuNAND，并且想将之前EmuNAND中的数据迁移到新的SysNAND自制系统中，请在开始本部分操作之前先按照[迁移EmuNAND数据](move-emunand)一节进行。
{: .notice--info}

1. 关机，按住(Start)键开机，进入Luma3DS启动器菜单
1. 按(A)键进入GodMode9
1. 依次进入`[0:] SDCARD` -> `luma` -> `payloads`
1. 选中`start_SafeB9SInstaller.bin`文件，按(X)键删除
1. 按(A)键确认
1. 进入`[0:] SDCARD`
1. 选中`boot.firm`文件，按(Y)键复制
1. 按(B)键返回到主菜单
1. 进入`[1:] SYSNAND CTRNAND`
1. 按(Y)键粘贴一份`boot.firm`文件的副本
1. 选择"Copy path(s)"（复制路径）
1. 按(A)键解锁SysNAND(lvl1)写保护，然后按照提示输入按键组合
1. 选中`arm9loaderhax.bin`文件，按(X)键删除
  + 如果你没有看到这个文件，继续进行接下来的教程
1. 按(A)键确认
1. 按(B)键返回到主菜单
1. 进入`[0:] SDCARD`
1. 选中`luma`文件夹，按(Y)键复制
1. 按(B)键返回到主菜单
1. 依次进入`[1:] SYSNAND CTRNAND` -> `rw`
1. 选中`luma`文件夹，按(X)键删除
  + 如果你没有看到这个文件夹，继续进行接下来的教程
1. 按(A)键确认
1. 按(Y)键粘贴之前从SD卡根目录复制的`luma`文件夹
1. 按(Start)键重启

##### 第五部分 - 安装Luma3DS升级器

1. 运行FBI
1. 依次进入`SD` -> `cias`
1. 选择`lumaupdater.cia`
1. 选择"Install CIA"选项，按(A)键确认
1. 按(Home)键退出FBI

___

现在你可以删除SD卡上任何与arm9loaderhax相关的文件，如SD卡根目录的`arm9loaderhax.bin`文件和`files9`目录下的`aeskeydb.bin`文件。
{: .notice--info}

注意`/boot9strap/`目录下的`.bak`文件仅在安装boot9strap失败的时候有用。在你安装成功后，你可以删除整个`boot9strap`文件夹。
{: .notice--info}

这个改版的Luma3DS升级器将下载和提取最新的Luma3DS `boot.firm`文件。
{: .notice--info}

{% capture notice-6 %}
你可以按下(Select)键开机，进入Luma3DS的设置菜单。
你可以按下(Start)键开机，运行Luma启动器菜单（注意只有在Luma3DS检测到多于一个payload的时候才会显示菜单）。
你可以按下(Start) + (Select) + (X)键开机，导出ARM11 bootrom（`boot11.bin`），ARM9 bootrom（`boot9.bin`），以及你设备独有的OTP(`OTP.bin`)到SD卡的`/boot9strap`目录下（该过程没有任何提示信息）。
你可以在系统启动时按下(L) + (Down) + (Select)键，打开Luma3DS内置的Rosalina菜单。如果想了解Rosalina的全部特性，参见[Luma3DS v8.0 Release](https://github.com/AuroraWright/Luma3DS/releases/tag/v8.0)。
{% endcapture %}

<div class="notice--info">{{ notice-6 | markdownify }}</div>
