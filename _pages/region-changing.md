---
title: "区域变更"
---

本节是关于变更自制系统SysNAND所在区域的附加章节。通过安装对应区域的9.2.0 CTRTransfer image（CTR迁移镜像），你可以将机器变更到你想要的区域。
{: .notice--primary}

**Luma3DS已经支持跨区游戏和独立的[title区域模拟](https://github.com/AuroraWright/Luma3DS/wiki/Options-and-usage)，区域变更已经变得几乎没有必要。**
{: .notice--info}

你需要一个能进行BT下载的软件，如[Deluge](http://dev.deluge-torrent.org/wiki/Download)、[aria2](https://aria2.github.io/)或迅雷，才能下载本节教程中的[磁力链接](http://baike.baidu.com/item/%E7%A3%81%E5%8A%9B%E9%93%BE%E6%8E%A5)。
{: .notice--success}

请注意，如果在SD卡的`/luma/payloads/`目录下有除了`GodMode9.firm`的其他payload文件，按住(Start)键开机的时候会显示“启动器菜单”，你需要用方向键和(A)键选择"GodMode9"才能继续进行教程中接下来的步骤。
{: .notice--info}

本过程将解绑你的NNID和你的系统，因为它们不再兼容。NNID在创建后就会被锁定为当前机器所在的区域，除非经过[一个非常复杂和进阶的流程](https://gist.githubusercontent.com/yifanlu/e80db121d38aceb8cca0e03cefd5853b/raw/3c4dd89869156ca0f945a2791e699acfdb32b510/gistfile1.txt)不能在区域间迁移。
{: .notice--warning}

区域变更后，只有**从未访问过eShop的新3DS**和**任何老3DS**可以在新的区域创建一个新的NNID并访问eShop。已经在原来的区域访问过eShop的新3DS将不能创建一个新的NNID，并在新的区域上访问eShop！
{: .notice--warning}

请注意，有时候eShop在某些本应该可以访问的设备上还是莫名其妙地无法正常访问。这完全取决于任天堂的服务器，我真的背不了这个锅:P
{: .notice--warning}

同样请注意，有时候eShop在某些本不应该能访问的设备上莫名其妙地可以正常访问（如某些新3DS）。造成该情况的原因目前未知。
{: .notice--warning}

使用CTRTransfer进行区域变更（本节教程使用的就是此法）似乎会造成重启补丁失效，原因未知。老3DS用户将无法运行扩展内存模式的游戏（如怪物猎人，任天堂明星大乱斗，和精灵宝可梦日/月），除非进行系统格式化。
{: .notice--warning}

不要在系统版本小于11.4.0的新2DS上进行系统格式化，否则你将无法完成初始设置！
{: .notice--danger}

**你必须已经安装了Luma3DS + boot9strap或arm9loaderhax中的一个，才能进行本节操作。**
{: .notice--danger}

#### 你需要

* 最新版的[GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* 最新版的[FBI](https://github.com/Steveice10/FBI/releases/latest) *（`.3dsx`文件）*
* [`ctrtransfer_ticket_copy.gm9`]({{ base_path }}/gm9_scripts/ctrtransfer_ticket_copy.gm9)
* 对应你设备和区域的9.2.0 CTRTransfer镜像（下载链接均是磁力链格式）
* 你想更换到的区域的9.2.0 ctr迁移镜像
  + <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [新3DS或新2DS - 9.2.0 - 欧版 - CTRTransfer](magnet:?xt=urn:btih:fed7bfeec0e52b42a77467cfb6ffd3e9dd2d5a70&dn=9.2.0-20E%5FCTRTransfer%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  + <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [新3DS或新2DS - 9.2.0 - 日版 - CTRTransfer](magnet:?xt=urn:btih:b22d67fd02b3b0e30ac991e451db0f2d32e7beca&dn=9.2.0-20J%5FCTRTransfer%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  + <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [新3DS或新2DS - 9.2.0 - 美版 - CTRTransfer](magnet:?xt=urn:btih:985d47442dc470d1b9f908256bed041c63885f60&dn=9.2.0-20U%5FCTRTransfer%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
~
  + <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [老3DS或老2DS - 9.2.0 - 欧版 - CTRTransfer](magnet:?xt=urn:btih:8d6142313971b08f92257e7fb1c1d5689e34ed78&dn=9.2.0-20E%5FCTRTransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  + <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [老3DS或老2DS - 9.2.0 - 日版 - CTRTransfer](magnet:?xt=urn:btih:24ad2b85e67013ef1f91178dca7ad2e40663b9b2&dn=9.2.0-20J%5FCTRTransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  + <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [老3DS或老2DS - 9.2.0 - 美版 - CTRTransfer](magnet:?xt=urn:btih:1dc79a2a0babb45497961888f369423a93135e2b&dn=9.2.0-20U%5FCTRTransfer%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)

#### 操作指南

##### 第一部分 - 准备工作

1. 关机
1. 取出SD卡，将SD卡插入电脑
1. 在SD卡根目录创建名为`cias`的文件夹（如果不存在的话）
1. 解压`GodMode9`压缩包，复制`GodMode9.firm`文件（arm9loaderhax用户请使用`GodMode9.bin`文件）到SD卡的`/luma/payloads/`目录下，复制`gm9`文件夹到SD卡根目录下
1. 复制`ctrtransfer_ticket_copy.gm9`文件到SD卡的`/gm9/scripts/`目录下
1. 从CTRTransfer镜像压缩包中复制 9.2.0 的`.bin`和`.bin.sha` 到SD卡的`/gm9/`目录
1. 复制`FBI.3dsx`到SD卡的`/3ds/`目录下
1. 将SD卡插回你的机器

##### 第二部分 - CTRTransfer

1. 按住(Start)键开机，运行GodMode9
1. 如果提示你创建文件备份，按(A)键执行，然后按(A)键继续教程
1. 进入`[0:] SDCARD` -> `gm9`
1. 选中CTRTransfer`.bin`文件，然后按(A)键
1. 选择"CTRNAND options..."
1. 选择"Transfer image to CTRNAND"（转移镜像到CTRNAND）
1. 如果出现提示，选择"Transfer to SysNAND"
  + 如果你有EmuNAND，该提示才会出现
1. 按(A)键解锁(lvl1)写保护，然后输入提示的按键组合
  + 这一步需要较长时间
1. 完成后，按(A)键继续
1. 按(B)键两次返回主菜单
1. 按(Home)键打开行动菜单
1. 选择"More..."（更多）
1. 选择"Scripts..."（脚本）
1. 选择"ctrtransfer_ticket_copy"
1. 出现提示时，按(A)键继续
1. 按(A)键继续
1. 按(A)键重新加上写保护
1. 按(Start)键重启你的机器
1. 进入"System Settings"（系统设置）、"Other Settings"（其它设置），移动到最右边一页，选择"System Update"（系统升级），将你的系统升级到最新版本
  + 使用B9S + Luma（或者其它自制系统）进行系统升级很安全
  + 如果出现错误，将你的DNS设置改为"auto"（自动）模式

##### 第三部分 - 运行FBI

1. 运行Download Play应用
1. 同时按(L) + (Down) + (Select)键，打开Rosalina目录
1. 选择"Miscellaneous options"（杂项）
1. 选择"Switch the hb. title to the current app."
1. 按(B)键继续
1. 按(B)键返回Rosalina主菜单
1. 按(B)键退出Rosalina主菜单
1. 按(Home)键，然后关闭Download Play
1. 运行Download Play应用
1. 你的机器现在应该开始加载自制程序启动器了

##### 第四部分 - 重装Tickets

如果脚本提示没有找到"user tickets"，让你跳过本部分，请跳过这一部分。
{: .notice--info}

1. 从自制程序列表中选择FBI运行
1. 进入`SD` -> `gm9` -> `out`
1. 选择"ctrtransfer_tickets"
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

##### 第五部分 - 删除CTRTransfer镜像

1. 按住(Start)键开机，运行GodMode9
1. 进入`[0:] SDCARD` -> `gm9`
1. 选中CTRTransfer镜像`.bin`文件，按(X)键删除
1. 按(A)键确认
1. 按(Start)键重启

---

老3DS/2DS用户需要格式化机器（使用TinyFormat或系统设置）才能玩扩展内存模式的游戏（如怪物猎人，任天堂明星大乱斗，和精灵宝可梦日/月）。
{: .notice--info}
