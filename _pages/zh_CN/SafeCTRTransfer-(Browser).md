---
title: "SafeCTRTransfer（浏览器）"
permalink: /safectrtransfer-(browser).html
lang: zh_CN
---

如果你的3DS之前已经破解，并安装了基于EmuNAND的自制系统，请务必注意本教程仅适用于SysNAND，教程内的步骤应当应用在你的SysNAND上。注意EmuNAND和RedNAND是[同一概念](http://3dbrew.org/wiki/NAND_Redirection)的两种略微不同的实现。
{: .notice--info}

如果你的设备是**新3DS**或者**2DS**，在降级到了2.1.0系统时**无线连接没有开启**，你可以将充电器断开并将电池拿下来，等待数秒后再开机，即可重新开启无线连接。
{: .notice--info}

如果你一直在使用新3DS的SD卡管理功能进行文件传输，请注意该功能在2.1.0系统上不可用。请确保在开始本教程之前，你手头已有一个SD卡读卡器。
{: .notice--info}

**你需要一个能进行BT下载的软件，如[Deluge](http://dev.deluge-torrent.org/wiki/Download)、[aria2](https://aria2.github.io/)或迅雷，才能下载本节教程中的[磁力链接](http://baike.baidu.com/item/%E7%A3%81%E5%8A%9B%E9%93%BE%E6%8E%A5)。**
{: .notice--info}

**目前在进行完2.1.0 ctr转移之后，你的3DS需要能连接上互联网才能继续进行教程。**
{: .notice--warning}

**在进行2.1.0 ctr转移之前，请确保你已禁用了家长控制（parental control）。如果你不知道密码，参见[这里](https://mkey.salthax.org/)。如果绑定的NNID是13岁以下儿童，无法禁用家长控制，你也可以将所有家长控制选项设为“无限制”（"do not restrict"）。**
{: .notice--warning}

**进行ctr转移会删除所有已安装的游戏，直到恢复备份后才能复原。**
{: .notice--danger}

**永远不要在低于6.0.0版本的2DS上进行格式化，否则你将无法完成初始化步骤，导致变砖！**
{: .notice--danger}

**千万不要在运行2.1.0版本系统（实际上是老3DS的固件）的新3DS上升级系统，否则会变砖！你必须先恢复NAND备份，或者ctr转移回新3DS的固件！**
{: .notice--danger}

{% capture notice %}
**将2.1.0系统版本的新3DS留在睡眠模式下，会导致不可恢复的变砖！**    
**仅在开机合盖时会发生这种情况。关机状态下合盖不受影响。**    
**3DS只有在合盖时才会进入睡眠模式，不会出现开盖下定时进入睡眠模式或者类似的情况。**    
**一旦系统版本降级到2.1.0后，你应该立刻进行下一步的操作，避免这种情况的发生！**    
{% endcapture %}

<div class="notice--danger">{{ notice | markdownify }}</div>

#### 步骤概览

在本节教程中，我们将向你的设备的[CTRNAND](https://www.3dbrew.org/wiki/Flash_Filesystem#CTR_partition)分区刷入2.1.0版本的系统，以便利用2.1.0中的一个漏洞来提取每个设备独一无二的[OTP](otp-info)文件。这个OTP文件将被用来安装arm9loaderhax，并且**不能**和其它设备共享。

刷入的过程将[安装预先制作好的ctr转移镜像](https://www.reddit.com/r/3dshacks/comments/4zhe4a/)，其中包含2.1.0版本的系统文件；复制你设备所独有的文件（例如`moveable.sed`和`SecureInfo_A`），并修复title数据库。

#### 你需要

* 最新版本的[SafeCTRTransfer](https://github.com/d0k3/SafeCTRTransfer/releases/latest)
* 对应你设备和区域的 2.1.0 ctr转移文件（请注意下载链接为磁力链）
*（如果你的设备不在下面的区域中，请随便选一个）*:
  +    <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [新3DS或老3DS或2DS 2.1.0 - 欧版 - CTRTransfer](magnet:?xt=urn:btih:89acc9c1b488b8b38251de0ddf07975d6bd354a1&dn=2.1.0-4E%5FCTRTransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  +    <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [新3DS或老3DS或2DS 2.1.0 - 日版 - CTRTransfer](magnet:?xt=urn:btih:3dbb9c9c85a33c6242f424dcbaebcacdd8a5912b&dn=2.1.0-4J%5FCTRTransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  +    <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [新3DS或老3DS或2DS 2.1.0 - 美版 - CTRTransfer](magnet:?xt=urn:btih:1609ce9ee7b0ed9b6dea0b3e7cca4fc52dad6ff4&dn=2.1.0-4U%5FCTRTransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)

#### 操作指南

##### 第一部分 - 准备工作

1. 关机
1. 将SD卡插入电脑
1. 在SD卡根目录创建名为`ctrtransfer`的文件夹（如果没有的话）
1. 解压缩CTRTransfer`.zip`压缩包，复制2.1.0`.bin`和`.bin.sha`文件到SD卡的`/ctrtransfer/`目录下
1. 解压缩SafeCTRTransfer`.zip`压缩包，复制`Launcher.dat`和`SafeCTRTransfer.dat`文件到SD卡根目录
1. 将SD卡插回你的机器
1. 开机

#####　第二部分 - 运行SafeCTRTransfer

1. 打开浏览器，进入以下网址中的其中一个：
  + `https://dukesrg.github.io/?SafeCTRTransfer.dat`
  + `http://go.gateway-3ds.com/`
  + `http://www.reboot.ms/3ds/load.html?Launcher.dat`
  + `http://dukesrg.dynu.net/3ds/rop?GW17567.dat&Launcher.dat`
  + 如果第一个网址用不了，把剩下的都试一下（有些机器用不了第一个网址，有些用不了后三个）
  + 如果出现错误，参见[问题排查](troubleshooting#ts_browser)
1. 如果漏洞利用成功，SafeCTRTransfer将会启动

##### 第三部分 - CTR迁移

1. 允许SafeCTRTransfer进行初始化，并自动进行安全检查
  + 如果出现错误，确保SD卡上所有文件都在正确的位置，并且你的SD卡上有足够的剩余空间（参见[开始教程](get-started)页面）
1. 按照提示输入按键组合，确认进行CTR迁移到2.1.0
  + 该过程可能需要较长时间
  + 该过程将自动在`/ctrtransfer/`目录下为你的机器创建系统备份，文件名为`<serialnumber>_nand.bin`（serialnumber是你的设备的序列号）
  + 如果出现错误，参见[问题排查](troubleshooting#ts_transfer)
1. 迁移完成后，将SD卡从机器中取出，然后重启
  + 重启大约需要2秒才能触发
  + 在2.1.0系统上，如果在主菜单加载之前插入了SD卡，3DS将会黑屏。
  + 每次在2.1.0系统上重启时，你都需要在启动前把SD卡拔出，等主菜单加载完成后再将SD卡插回。
  + 请先不要将SD卡插回3DS。接下来的教程中，你需要复制一些文件到SD卡里。
  + 在下一页教程中进行系统还原后，该问题就会被修复。

---

*某些机器在2.1.0系统版本下屏幕显示会出现拉伸和变色，属于正常现象。在你恢复了备份的NAND之后，这种现象就会消失*
{: .notice--info}

{% capture notice %}
**将2.1.0系统版本的新3DS留在睡眠模式下，会导致不可恢复的变砖！**
**仅在开机合盖时会发生这种情况。关机状态下合盖不受影响。**
**你的机器只有在合盖时才会进入睡眠模式，不会出现开盖下定时进入睡眠模式或者类似的情况。**
**你应该立刻进行下一步的操作，避免这种情况的发生！**
{% endcapture %}

<div class="notice--danger">{{ notice | markdownify }}</div>

下一步请进入[安装arm9loaderhax](installing-arm9loaderhax)
{: .notice--primary}

