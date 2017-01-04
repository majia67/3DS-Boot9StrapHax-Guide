---
layout: splash
permalink: /
title: "教程首页"
header:
  overlay_color: "#5e616c"
  overlay_image: images/home-page-feature.jpg
  overlay_filter: 0.5
  cta_label: "开始教程"
  cta_url: "/get-started"
  caption:
excerpt: '利用arm9loaderhax实现3DS运行自制固件的完整教程。<br />'
---

{% capture notice-home %}
**本教程仅适用于零售版的3DS (机器并非来自Nintendo Developer Program) ！    
如果你的3DS属于开发机 ("PANDA"或"SNAKE")，请参见[devGuide](https://dev.3ds.guide)**
{% endcapture %}

<div class="notice--danger">{{ notice-home | markdownify }}</div>

**要想使用本教程提供的[磁力链](https://zh.wikipedia.org/zh-hans/%E7%A3%81%E5%8A%9B%E9%93%BE%E6%8E%A5)下载地址，你需要一个类似于[Deluge](http://dev.deluge-torrent.org/wiki/Download)的torrent客户端。**
{: .notice--info}

**请先阅读完本页面再开始操作。**
{: .notice--warning}

## 什么是自制程序？

[**Homebrew（自制程序）**](https://en.wikipedia.org/wiki/List_of_homebrew_video_games) 通常指未经任天堂授权的软件。它能让你运行自制游戏，使用像编辑和备份存档的工具，以及运行模拟器。

大多数情况下，只需使用Nintendo 3DS Sound（任天堂3DS声音）就能在你的3DS上100%免费运行自制程序。有些商业游戏和浏览器中也存在漏洞，可以使你运行自制程序。

## 什么是自制固件？

**Custom Firmware（自制固件）** ("CFW") 可以使你进行自制程序无法轻易做到的更高级的破解。例如，签名补丁可以使你安装未签名的程序，并让它们出现在桌面菜单中。

CFW可以很容易地在系统版本11.1.0及以下的设备上安装。其它版本的设备可以将固件进行降级（firmware downgrade）。

## 本教程将安装什么？

本教程可以帮助你将一个完全没有修改过的装有完整系统软件的3DS变成一个arm9loaderhax破解过的自制系统。在某些版本的机器上，本教程会使用自制程序作为手段，但是安装自制固件才是最终目的。

Arm9loaderhax是一种最新最棒的引导自制固件的方法，只需启动时的几毫秒就能让你获得系统几乎全部权限，类似于Wii上面BootMii的作用。

Arm9loaderhax相较于其它运行自制固件的办法有很多优势，所以建议使用本教程来破解你的3DS，而不是其它那些依赖已经过时的软件（例如menuhax或rxTools）的教程。

## 我能用自制固件做什么？

+ 跨区运行所有游戏卡带和eShop游戏
+ 使用玩家自制的[主题](https://3dsthem.es/)和[卡贴](https://badges.3dsthem.es/)来自定义你的桌面菜单。
+ 对你自己的游戏进行"ROM hacks"
+ 进行游戏录像和截屏
+ [备份、修改和恢复](https://gbatemp.net/threads/release-jks-savemanager-homebrew-cia-save-manager.413143/)游戏存档
+ 使用模拟器（如RetroArch或其它独立模拟器）运行老系统的游戏（在新3DS上效果最佳）
+ 往桌面菜单安装自制软件
+ 将游戏卡带的内容导出为可安装的格式，从而可以无需卡带运行游戏
+ 仅限新3DS：使用NTR CFW在线将你的游戏画面输出到PC
+ 运行许多被禁的老NDS卡带
+ 安全地升级到最新版本的系统，无需担心升级后无法访问自制程序

## 开始本教程之前我需要知道什么？

+ **在开始之前，你要想清楚，破解3DS是有风险的: 每次你修改系统的时候，都有可能会使你的3DS不可恢复的变砖。这种情况很少见，但是仍然存在这种可能性，所以请确保你操作的时候完全按照本教程的步骤。**
+ 如果你之前破解过你的3DS并安装了EmuNAND，想将原EmuNAND中的内容转移到SysNAND CFW中，请依操作进行，并在[Installing arm9loaderhax](installing-arm9loaderhax)这一步中依照提示还原的你EmuNAND。
+ 本教程适用于所有区域的新3DS，老3DS和2DS，固件版本在11.2.0及以下*（除神游/台版机）*.
+ 如果一切顺利，在安装完自制固件后你不会丢失任何数据（包括游戏、NNID、存档等）。
+ **确保你的3DS充满电，并在操作过程中接上电源，以防止因电池耗尽而造成数据丢失或机器损坏！**
+ 你的SD卡的分区表必须是[MBR，而不是GPT](http://www.howtogeek.com/245610/)格式的(机器自带的SD卡的分区表是MBR格式的)。
+ 如果你需要格式化一张新的SD卡，你可以使用[`guiformat`](http://www.ridgecrop.demon.co.uk/index.htm?guiformat.htm)，并将Allocation Unit Size设置为32K。
+ 2DS所需的软件和老3DS一致，因而任何适用于老3DS的步骤也同样适用于2DS。
