---
title: "区域变更"
permalink: /region-changing.html
lang: zh_CN
ref: region-changing
---

本节是关于变更arm9loaderhax自制系统SysNAND所在区域的附加章节。通过安装对应区域的9.2.0 CTRTransfer image（CTR迁移镜像），你可以将机器变更到你想要的区域。
{: .notice--primary}

**Luma3DS已经支持跨区游戏和独立的[title区域模拟](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage)，区域变更已经变得几乎没有必要。**
{: .notice--info}

你需要一个能进行BT下载的软件，如[Deluge](http://dev.deluge-torrent.org/wiki/Download)、[aria2](https://aria2.github.io/)或迅雷，才能下载本节教程中的[磁力链接](http://baike.baidu.com/item/%E7%A3%81%E5%8A%9B%E9%93%BE%E6%8E%A5)。
{: .notice--info}

本过程将解绑你的NNID和你的系统，因为它们不再兼容。NNID在创建后就会被锁定为当前机器所在的区域，除非经过[一个非常复杂和进阶的流程](https://gist.githubusercontent.com/yifanlu/e80db121d38aceb8cca0e03cefd5853b/raw/3c4dd89869156ca0f945a2791e699acfdb32b510/gistfile1.txt)不能在区域间迁移。
{: .notice--warning}

区域变更后，只有**从未访问过eShop的新3DS**和**任何老3DS**可以在新的区域创建一个新的NNID并访问eShop。已经在原来的区域访问过eShop的新3DS将不能创建一个新的NNID，并在新的区域上访问eShop！
{: .notice--warning}

请注意，有时候eShop在某些本应该可以访问的设备上还是莫名其妙地无法正常访问。这完全取决于任天堂的服务器，我真的背不了这个锅:P
{: .notice--warning}

同样请注意，有时候eShop在某些本不应该能访问的设备上莫名其妙地可以正常访问（如某些新3DS）。造成该情况的原因目前未知。
{: .notice--warning}

使用CTRTransfer进行区域变更（本节教程使用的就是此法）似乎会造成重启补丁失效，原因未知。老3DS用户将无法运行扩展内存模式的游戏（如怪物猎人，任天堂明星大乱斗，和精灵宝可梦日/月），除非进行系统格式化（详情见本节教程最后）。
{: .notice--warning}

**你必须已经安装了arm9loaderhax + Luma3DS才能进行本节操作。**
{: .notice--danger}

#### 你需要

* 最新版的[GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* 最新版的[FBI](https://github.com/Steveice10/FBI/releases/latest)
* 你想更换到的区域的9.2.0 ctr迁移镜像
  + <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [新3DS 9.2.0 - 欧版 - CTRTransfer](magnet:?xt=urn:btih:fed7bfeec0e52b42a77467cfb6ffd3e9dd2d5a70&dn=9.2.0-20E%5FCTRTransfer%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  + <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [新3DS 9.2.0 - 日版 - CTRTransfer](magnet:?xt=urn:btih:b22d67fd02b3b0e30ac991e451db0f2d32e7beca&dn=9.2.0-20J%5FCTRTransfer%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  + <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [新3DS 9.2.0 - 美版 - CTRTransfer](magnet:?xt=urn:btih:985d47442dc470d1b9f908256bed041c63885f60&dn=9.2.0-20U%5FCTRTransfer%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
~
  + <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [老3DS 或 2DS 9.2.0 - 欧版 - CTRTransfer](magnet:?xt=urn:btih:8d6142313971b08f92257e7fb1c1d5689e34ed78&dn=9.2.0-20E%5FCTRTransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  + <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [老3DS 或 2DS 9.2.0 - 日版 - CTRTransfer](magnet:?xt=urn:btih:24ad2b85e67013ef1f91178dca7ad2e40663b9b2&dn=9.2.0-20J%5FCTRTransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  + <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [老3DS 或 2DS 9.2.0 - 美版 - CTRTransfer](magnet:?xt=urn:btih:1dc79a2a0babb45497961888f369423a93135e2b&dn=9.2.0-20U%5FCTRTransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)

#### 操作指南

##### 第一部分 - 准备工作

1. 关机
1. 取出SD卡，将SD卡插入电脑
1. 在SD卡根目录创建名为`cias`的文件夹（如果不存在的话）
1. 解压缩GodMode9压缩包，复制`GodMode9.bin`文件到SD卡的`/luma/payloads/`目录下，并将`GodMode9.bin`重命名为`start_GodMode9.bin`
1. 从CTRTransfer压缩包中提取9.2.0 CTRTransfer镜像`.bin`文件，复制到SD卡的`/files9/`目录下
1. 解压缩FBI`.zip`压缩包，复制`FBI.cia`文件到SD卡的`/cias`目录下
1. 将SD卡插回你的机器

##### 第二部分 - CTRTransfer

1. 按住(Start)键开机，进入GodMode9
1. 进入`SDCARD` -> `files9`
1. 选中CTRTransfer`.bin`文件，然后按(A)键
1. 选择"CTRNAND options..."
1. 选择"Transfer image to CTRNAND"（转移镜像到CTRNAND）
1. 如果出现提示，选择"Transfer to SysNAND"
  + 如果你有EmuNAND，该提示才会出现
1. 按(A)键解锁(lvl1)写保护，然后输入提示的按键组合
  + 这一步需要较长时间
1. 完成后，按(A)键继续
1. 按(B)键两次返回主菜单
1. 进入`SYSNAND CTRNAND` -> `dbs`
1. 选择`ticket.bak`文件，按(A)键选中，然后选择"Mount as ticket.db"
1. 如果存在`eshop`文件夹，按住(R)键的同时按(A)键选中，然后选择"Copy to 0:/gm9out"
  + 如果你有许多tickets，这一步可能需要较长时间
  + 完成后，按(A)键继续
1. 如果存在`unknown`文件夹，按住(R)键的同时按(A)键选中，然后选择"Copy to 0:/gm9out"
  + 如果你有许多tickets，这一步可能需要较长时间
  + 完成后，按(A)键继续
1. 按(Start)键重启你的机器
1. 进入"System Settings"（系统设置）、"Other Settings"（其它设置），移动到最右边一页，选择"System Update"（系统升级），将你的系统升级到最新版本
  + **请注意，因为11.4.0版本的系统最近刚发布，在上面运行Luma3DS还有一些bug（DS和GBA游戏无法运行）。并且NTR CFW还不与11.4.0版本的系统兼容。你可以先不升级系统，等新版的Luma3DS修复bug后再升级**
  + 使用A9LH + Luma（或者其它自制系统）进行系统升级很安全
  + 如果出现错误，将你的DNS设置改为"auto"（自动）模式

##### 第三部分 - 注入FBI

1. 按住(Start)键重启，进入GodMode9
1. 进入`SDCARD` -> `cias`
1. 选中`FBI.cia`文件，按(A)键，并选择"CIA image options..."（CIA镜像选项），然后选择"Mount image to drive"（将镜像挂载到驱动器）
1. 选中`.app`文件，按(A)键，然后选择"NCCH image options"，并选择"Inject to H&S"
1. 按(A)键解锁SysNAND(lvl1)写保护，然后按照提示输入按键组合
1. 按(A)键继续
1. 按(Start)键重启
1. 如果你依然进入的是系统内置的健康与安全应用，并且之前曾经用Gateway进行过降级，参见这个[问题排查](troubleshooting#gw_fbi)

##### 第四部分 - 重装Tickets

如果在第二部分的操作中不存在`eshop`或`unknown`文件夹，跳过这一部分
{: .notice--info}

1. 在桌面菜单中运行健康与安全（Health & Safety）应用（现在应该是FBI）
1. 进入`SD` -> `cias`
1. 选择`FBI.cia`
1. 选择"Install"（安装）选项，然后按(A)键确认
1. 按(B)键返回SD卡根目录
1. 选择"gm9out"
1. 对`eshop`和`unknown`文件夹执行如下操作（如果只有其中一个文件夹，则只需对其执行操作）：
  + 进入该文件夹
  + 选择"files9"
  + 选择"\<current directory>"
  + 选择"Install and delete all tickets"
  + 等待。系统可能看起来会卡住，多给它一点时间。
  + 按(A)键确认
  + 按(B)键放弃从CDN安装tickets
1. 按(Home)键退出FBI

##### 第五部分 - 区域设置

1. 打开系统设置（System Settings）
2. 依次选择"Other Settings"，"Profile"，"Region Settings"
3. 选择你变更区域后的国家
4. 如果出现提示，无需设置州（state）
5. 将变更区域后的自制系统SysNAND升级到最新版本

##### 第六部分 - 恢复“健康与安全”应用

1. 按住(Start)键重启，进入GodMode9
1. 按(Home)键打开菜单
1. 选择"More..."
1. 选择"Restore H&S"（恢复健康与安全应用）
1. 按(A)键解锁SysNAND(lvl1)写保护，然后按照提示输入按键组合

##### 第七部分 - 移除CTR转移镜像

1. 进入`SDCARD` -> `files9`
1. 选中CTR转移镜像`.bin`文件，按(X)键删除
1. 按(A)键确认
1. 按(Start)键重启

---

老3DS/2DS可能需要格式化机器（使用TinyFormat或系统设置）才能玩扩展内存模式的游戏（如怪物猎人，任天堂明星大乱斗，和精灵宝可梦日/月）。
{: .notice--info}
