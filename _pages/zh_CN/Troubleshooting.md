---
title: "问题排查"
permalink: /troubleshooting.html
lang: zh_CN
ref: troubleshooting
---

如果你启动不了你的机器，请参阅本页面中的相关章节，并按照教程执行。问题解决后，便可回到主教程继续进行。
（本页面内容较多，请尝试使用Ctrl+F查找相关内容）
{: .notice--primary}

**如果尝试了本页面的指导后问题仍未解决，请将SD卡上生成的所有.log文件复制到[Gist](https://gist.github.com/)，然后向我们求助，并附上你对问题的详细描述以及你尝试过的解决方案。**
{: .notice--info}

你需要一个能进行BT下载的软件，如[Deluge](http://dev.deluge-torrent.org/wiki/Download)、[aria2](https://aria2.github.io/)或迅雷，才能下载本节教程中的[磁力链接](http://baike.baidu.com/item/%E7%A3%81%E5%8A%9B%E9%93%BE%E6%8E%A5)。
{: .notice--success}

## <a name="twl_broken" />完成本教程后DSi / DS功能失效

#### 你需要

* 针对你设备的TWL_FIRM `.cia`文件
  + <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [`新3DS TWL_FIRM - v9936.cia`](magnet:?xt=urn:btih:eab8558c97b18b1f329a2bfcc3c899b84c082a27&dn=New%5F3DS%20TWL%5FFIRM%20-%20v9936.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  + <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [`老3DS TWL_FIRM - v8817.cia`](magnet:?xt=urn:btih:17511eadb6e6f3ff22d04f90644e37bd2d96ca43&dn=Old%5F3DS%20TWL%5FFIRM%20-%20v8817.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [`TWL Version Data - v0.cia`](magnet:?xt=urn:btih:4a106681407fede5de95cc8bda635432481f6b5d&dn=TWL%20Version%20Data%20-%20v0.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [`DS Internet - v2048.cia`](magnet:?xt=urn:btih:2b9df8496922f2546dfb0b01220068ce53c19d3d&dn=DS%20Internet%20-%20v2048.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [`DS Download Play - v1024.cia`](magnet:?xt=urn:btih:b581d3c5d98f5e621fddfc1ce5704bb45bf05a8c&dn=DS%20Download%20Play%20-%20v1024.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* <i class="fa fa-magnet" aria-hidden="true" title="这个下载链接是磁力链格式的。请使用BT种子客户端进行下载。"></i> - [`Nintendo DS Cart Whitelist - v11264.cia`](magnet:?xt=urn:btih:7b90d506ad032a581a00035616eaa17a68c48eff&dn=Nintendo%20DS%20Cart%20Whitelist%20-%20v11264.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)

#### 操作指南

##### 第一部分 - 准备工作

1. 在你的SD卡根目录新建一个叫`cias`的文件夹，如果还不存在的话
1. 将`TWL Version Data - v0.cia`文件复制到SD卡的`/cias/`目录下
1. 将`DS Download Play - v1024.cia`文件复制到SD卡的`/cias/`目录下
1. 将`DS Internet - v2048.cia`文件复制到SD卡的`/cias/`目录下
1. 将`Nintendo DS Cart Whitelist - v11264.cia`文件复制到SD卡的`/cias/`目录下
1. 将`New_3DS TWL_FIRM - v9936.cia`或`Old_3DS TWL_FIRM - v8817.cia`文件复制到SD卡的`/cias/`目录下

##### 第二部分 - 安装titles

1. 打开FBI
1. 选择"SD"
1. 进入"cias"
1. 选择"\<current directory>"
1. 选择"Install and delete all CIAs"
1. 按home键退出

## <a name="rm_nnid" />清除NNID而无需格式化设备

#### 你需要

* 最新版的[GodMode9](https://github.com/d0k3/GodMode9/releases/latest)

#### 操作指南

1. 解压`GodMode9`压缩包，复制`GodMode9.bin`到你SD卡的`/luma/payloads/`目录下
1. 按住(Start)键重启，进入Luma3DS启动器菜单
1. 按(A)键进入GodMode9
1. 依次选择进入`[1:] SYSNAND CTRNAND` -> `data` -> (32位用户ID) -> `sysdata` -> `00010038`
1. 在`00000000`上，按住(R)键的同时按下(X)键，以重命名这个文件
1. 按一次(Up)键，将文件名改为`10000000`
1. 按(A)键保存更改
1. 按(A)键解锁SysNAND写入，并输入提示的按键组合
1. 返回到主菜单
1. 按(Start)键重启

## <a name="gw_fbi" />在Gateway降级过的设备上无法注入Health & Safety应用
这一因为Gateway的降级方法非常糟糕，会在系统中留下每个app降级前后的两个版本，其中一个不再使用。这会迷惑H&S注入程序，使它注入到错误的版本中。

请注意：某些版本的Luma3DS只会在检测到多于一个payload时显示Luma3DS启动器菜单。如果只检测到一个payload，按住(Start)键启动将直接运行GodMode9。
{: .notice--info}

#### 操作指南

1. 按住(Start)键开机，进入Luma3DS启动器菜单
1. 按(A)键进入GodMode9
1. 依次选择`[1:] SYSNAND CTRNAND` -> `title` -> `00040010`
1. 移动到你的设备和区域所对应的文件夹：
  + **老3DS 欧版**: `00022300` -> `content`
  + **老3DS 日版**: `00020300` -> `content`
  + **老3DS 美版**: `00021300` -> `content`
  + **新3DS 欧版**: `20022300` -> `content`
  + **新3DS 日版**: `20020300` -> `content`
  + **新3DS 美版**: `20021300` -> `content`
1. 注意，文件夹里有两组app和tmd文件，一组带有大写的后缀（`.TMD`和`.APP`），一组带有小写的后缀（`.tmd`和`.app`）
1. 按住(R)键的同时，按(Y)键新建一个目录
1. 按(A)键确认目录名为`newdir`（叫什么名字不重要）
1. 按(A)键解锁SysNAND写入，并输入提示的按键组合
1. 在每个大写字母后缀（`.TMD`和`.APP`）的文件上按(L)键选中它们
1. 按(Y)键复制这些文件
1. 进入`newdir`文件夹
1. 按(Y)键粘贴这些文件
1. 选择"Move path(s)"
1. 大写字母后缀的文件将被移动到`newdir`文件夹下
1. 按(Start)键重启
1. 返回到[收尾工作](finalizing-setup)一节，重新尝试FBI注入
1. 如果还是不能注入， 将大写字母后缀的文件移动回`content`文件夹，然后将小写字母后缀的文件移动到`newdir`文件夹中，再返回到[安装arm9loaderhax](installing-arm9loaderhax)一节，重新尝试FBI注入

## <a name="ts_browser" />基于浏览器的漏洞利用失效
基于浏览器的漏洞利用（例如browserhax和2xrsa）通常不够稳定并经常崩溃，但有时也可以尝试按照下面的步骤修复：

1. 打开浏览器，进入浏览器设置页面
1. 移动到页面最底端，选择Initialize Savedata（初始化缓存）（有时也会叫做Clear All Save Data，清除所有缓存）
1. 再次尝试漏洞利用

## <a name="ts_sys_down" />启动到SysNAND黑屏

1. 尝试将SD卡拿出后启动系统，启动完成后将SD卡插回。
   1. 长按电源键关机
   1. 拔出你的SD卡
   1. 开机
   4. 桌面菜单出现后，插回SD卡
   5. 如果问题解决，你需要进入SD卡的`/Nintendo 3DS/(32位ID)/(32位ID)/extdata/00000000/`目录以清除主界面菜单的extdata
    + 欧版：删除 `00000098`
    + 日版：删除 `00000082`
    + 美版：删除 `0000008f`
    + 神游：删除 `000000A1`
    + 韩版：删除 `000000A9`
    + 台版：删除 `000000B1`
1. 尝试拔掉卡带（包括闪存卡带）开机
1. 如果你可以hardmod（硬改），并且有NAND备份，尝试将NAND备份写入SysNAND。
1. 尝试启动到恢复模式并升级你的系统
   *老3DS降级到2.1.0的系统后，该方法很可能会失效。*
   **新3DS降级到2.1.0后，尝试该方法会变砖。**
   1. 长按电源键关闭你的3DS。
   1. 按住(L) + (R) + (A) + (Up)键
   1. 按下电源键开机。
   1. 如果进入安全模式，*仅当你有最新固件版本进入HBL的方法，并且能进行降级的情况下*，才升级你的3DS，并再次尝试降级。
1. 你的3DS可能变砖了。请在[GitHub Issues](https://github.com/majia67/3DS-ARM9LoaderHax-Guide/issues)中提问，或者参考[FAQ](faq#faq_support)页面获取帮助。

## <a name="ts_sys_a9lh" />安装完arm9loaderhax后启动到SysNAND黑屏

1. 确保你有一个正常工作的payload
   1. 检查你的SD卡根目录有`boot.firm`文件。
1. 尝试重置Luma3DS的设置
   1. 删除SD卡上的`/luma/config.bin`文件
   1. 启动Luma3DS后重新设置
1. 尝试启动GodMode9
   1. 在Luma3DS上，按住(Start)键开机
1. 尝试删除桌面菜单的extdata
    1. 定位到sd卡的`/Nintendo 3DS/(32位ID)/(32位ID)/extdata/00000000/`
      + 欧版：删除 `00000098`
      + 日版：删除 `00000082`
      + 美版：删除 `0000008f`
      + 神游：删除 `000000A1`
      + 韩版：删除 `000000A9`
      + 台版：删除 `000000B1`
1. 尝试拔掉卡带（包括闪存卡带）开机
1. 如果你以前用Gateway降过级，确保你使用的是最新版的Luma3DS（版本号在v6.2.3及以上）
1. 如果你的系统版本在3.0.0到4.5.0之间，进行如下操作：
   + 确保你使用的是最新版的Luma3DS（版本号在v6.6及以上）
   + 下载[这个文件](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000056)并重命名为`firmware.bin`
   + 下载[这个文件](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk)
   + 复制`firmware.bin`和`cetk`到SD卡的`/luma/`文件夹下
   + 在你的3DS升级完成后，删除这两个文件
1. 尝试按照[9.2.0 ctr迁移](9.2.0-ctrtransfer)进行操作
1. 请在[GitHub Issues](https://github.com/majia67/3DS-ARM9LoaderHax-Guide/issues)中提问，或者参考[FAQ](faq#faq_support)页面获取帮助。

## <a name="ts_transfer" />进行SafeB9STransfer时出错

如果在进行SafeCTRTransfer时出现错误，你会被提示运行一个外部的payload来修复你的机器

#### 你需要

* 最新版的[GodMode9](https://github.com/d0k3/GodMode9/releases/)

#### 操作指南

1. 选择"弹出SD卡"
1. 将SD卡插入电脑
1. 解压GodMode9`.zip`压缩包，复制`GodMode9.bin`文件到SD卡的`/boot9strap/`目录下，并将其重命名为`payload.bin`
1. 将SD卡插回机器中
1. 选择"Run 0:/boot9strap/payload.bin"
1. 如果成功，你将进入GodMode9
1. 进入`[0:] SDCARD` -> `boot9strap`
1. 在`firm0firm1.bak`和`sector0x96.bak`文件上按(L)键标记它们
1. 按(Y)键复制文件
1. 按(B)键两次，返回主菜单
1. 进入`[S:] SYSNAND VIRTUAL`
1. 按(Y)键粘贴文件
1. 按(A)键确认
1. 按(A)键注入文件
1. 按(A)键解锁SysNAND覆盖
1. 按照提示输入按键组合，解锁SysNAND (lvl3)写保护
1. 完成后，按(A)键继续
1. 按(Start)键重启
1. 请将你遇到的问题反馈到[SafeB9SInstaller Issues Page](https://github.com/d0k3/SafeB9SInstaller/issues)

## <a name="ts_sys_blue" />启动时蓝屏（bootrom错误）

1. 你的机器已变砖。
1. 你需要[硬改](https://gbatemp.net/threads/414498/)或维修/更换你的机器。
