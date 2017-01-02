---
title: "问题排查"
permalink: /troubleshooting.html
---

如果你启动不了你的3DS，请参阅本页面中的相关章节，并按照教程执行。问题解决后，便可回到主教程继续进行。
（本页面内容较多，请尝试使用Ctrl+F查找相关内容）
{: .notice--primary}

**如果尝试了本页面的指导后问题仍未解决，请将SD卡上生成的所有.log文件复制到[Gist](https://gist.github.com/)，然后向我们求助，并附上你对问题的详细描述以及你尝试过的解决方案。**
{: .notice--info}

## <a name="twl_broken" />完成本教程后DSi / DS功能失效

#### 你需要

* 针对你设备的TWL_FIRM `.cia`文件
    + [`新3DS TWL_FIRM - v9936.cia`](magnet:?xt=urn:btih:eab8558c97b18b1f329a2bfcc3c899b84c082a27&dn=New%5F3DS%20TWL%5FFIRM%20-%20v9936.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
    + [`老3DS TWL_FIRM - v8817.cia`](magnet:?xt=urn:btih:17511eadb6e6f3ff22d04f90644e37bd2d96ca43&dn=Old%5F3DS%20TWL%5FFIRM%20-%20v8817.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* [`TWL Version Data - v0.cia`](magnet:?xt=urn:btih:4a106681407fede5de95cc8bda635432481f6b5d&dn=TWL%20Version%20Data%20-%20v0.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* [`DS Internet - v2048.cia`](magnet:?xt=urn:btih:2b9df8496922f2546dfb0b01220068ce53c19d3d&dn=DS%20Internet%20-%20v2048.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* [`DS Download Play - v1024.cia`](magnet:?xt=urn:btih:b581d3c5d98f5e621fddfc1ce5704bb45bf05a8c&dn=DS%20Download%20Play%20-%20v1024.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
* [`Nintendo DS Cart Whitelist - v11264.cia`](magnet:?xt=urn:btih:7b90d506ad032a581a00035616eaa17a68c48eff&dn=Nintendo%20DS%20Cart%20Whitelist%20-%20v11264.cia&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)

#### 操作指南

##### 第一部分 - 准备工作

1. 在你的SD卡根目录新建一个叫`cias`的文件夹，如果还不存在的话
1. 将`TWL Version Data - v0.cia`文件复制到SD卡的`/cias/`目录下
2. 将`DS Download Play - v1024.cia`文件复制到SD卡的`/cias/`目录下
3. 将`DS Internet - v2048.cia`文件复制到SD卡的`/cias/`目录下
4. 将`Nintendo DS Cart Whitelist - v11264.cia`文件复制到SD卡的`/cias/`目录下
5. 将`New_3DS TWL_FIRM - v9936.cia`或`Old_3DS TWL_FIRM - v8817.cia`文件复制到SD卡的`/cias/`目录下

##### 第二部分 - 安装titles

1. 打开FBI
3. 选择"SD"
4. 进入"cias"
8. 选择"\<current directory>"
9. 选择"Install and delete all CIAs"
8. 按home键退出

## <a name="rm_nnid" />清除NNID而无需格式化设备

#### 你需要

* 最新版的[GodMode9](https://github.com/d0k3/GodMode9/releases/)

#### 操作指南

1. 解压`GodMode9`压缩包，复制`GodMode9.bin`到你SD卡的`/luma/payloads`目录下，并重命名`GodMode9.bin`为`up_GodMode9.bin`
6. 按住(方向上)键启动机器，进入arm9loaderhax GodMode9
14. 依次选择进入`SYSNAND CTRNAND` -> `data` -> (32位用户ID) -> `sysdata` -> `00010038`
15. 在`00000000`上，按住(R)键的同时按下(X)键，以重命名这个文件
16. 按一次(方向上)键，将文件名改为`10000000`
17. 按(A)键保存更改
18. 按(A)键解锁SysNAND写入，并输入提示的按键组合
19. 返回到主菜单
16. 按(Start)键重启

## <a name="gw_fbi" />在Gateway降级过的设备上无法注入Health & Safety应用
这一因为Gateway的降级方法非常糟糕，会在系统中留下每个app降级前后的两个版本，其中一个不再使用。这会迷惑Decrypt9，使它注入错误的版本。

#### 你需要

* 最新版的[GodMode9](https://github.com/d0k3/GodMode9/releases/)

#### 操作指南

1. 解压`GodMode9`压缩包，复制`GodMode9.bin`到你SD卡的`/luma/payloads`目录下，并重命名`GodMode9.bin`为`up_GodMode9.bin`
2. 将SD卡插回3DS
5. 按住(方向上)键启动机器，进入arm9loaderhax GodMode9
2. 依次选择`SYSNAND CTRNAND` -> `title` -> `00040010`
7. 移动到你的设备和区域所对应的文件夹：
  + **老3DS 欧版**: `00022300` -> `content`
  + **老3DS 日版**: `00020300` -> `content`
  + **老3DS 美版**: `00021300` -> `content`
  + **新3DS 欧版**: `20022300` -> `content`
  + **新3DS 日版**: `20020300` -> `content`
  + **新3DS 美版**: `20021300` -> `content`
8. 注意，文件夹里有两组app和tmd文件，一组带有大写的后缀（`.TMD`和`.APP`），一组带有小写的后缀（`.tmd`和`.app`）
11. 按住(R)键的同时，按(Y)键新建一个目录
10. 按(A)键确认目录名为`newdir`（叫什么名字不重要）
6. 按(A)键解锁SysNAND写入，并输入提示的按键组合
9. 在每个大写字母后缀（`.TMD`和`.APP`）的文件上按(L)键选中它们
10. 按(Y)键复制这些文件
11. 进入`newdir`文件夹
12. 按(Y)键粘贴这些文件
13. 选择"Move path(s)"
14. 大写字母后缀的文件将被移动到`newdir`文件夹下
15. 按(Start)键重启
16. 返回到[安装arm9loaderhax](installing-arm9loaderhax)一节，重新尝试FBI注入
17. 如果还是不能注入， 将大写字母后缀的文件移动回`content`文件夹，然后将小写字母后缀的文件移动到`newdir`文件夹中，再返回到[安装arm9loaderhax](installing-arm9loaderhax)一节，重新尝试FBI注入

## <a name="ts_browser" />基于浏览器的漏洞利用失效
基于浏览器的漏洞利用（例如browserhax和2xrsa）通常不够稳定并经常崩溃，但有时也可以尝试按照下面的步骤修复：

1. 打开浏览器，进入浏览器设置页面
   1. 移动到页面最底端，选择Initialize Savedata（初始化缓存）（有时也会叫做Clear All Save Data，清除所有缓存） 
   2. 再次尝试漏洞利用

## <a name="ts_safe_a9lh" />系统启动进入了SafeA9LHInstaller
你将错误的`arm9loaderhax.bin`文件拷贝到SD卡中了（你应该仅将SafeA9LHInstaller压缩包中的`3ds`文件夹和`SafeA9LHInstaller.dat`文件拷贝到SD卡中）

1. 使用正确的`arm9loaderhax.bin`
   1. 将Luma3DS压缩包中的`arm9loaderhax.bin`文件拷贝到你的SD卡根目录
   2. 按Select键重启机器，并继续按照教程进行

## <a name="ts_safe_a9lh_screen" />SafeA9LHInstaller中屏幕闪烁
这种情况偶尔会发生，但原因未知。按键仍能正常工作，但屏幕会一直闪烁。 

1. 按照教程正常执行
   1. 按下Select键安装arm9loaderhax
   2. 机器会重启
      + 如果机器没有重启，等10秒，然后长按电源键关机。

## <a name="ts_steelhax" />系统传输steelhax后，目标3DS黑屏

这是因为你在steelhax安装程序中选择了错误的版本

1. 下载对应**目标3DS**版本的[otherapp payload](https://smealum.github.io/3ds/#otherapp)
    + 忽略“the NFIRM being downgraded”信息
    + 使用设置中显示的版本
2. 将“otherapp payload”改名为`steelhax_payload.bin`
3. 将`steelhax_payload.bin`复制到**目标3DS**的SD卡根目录
    + 覆盖任何已有的文件
4. 启动**Steel Diver: Sub Wars**时按住(B)键

## <a name="ts_dsiware" />完成DSiWare降级后，我破解过的DSiWare不能正常工作

3. 按住(Start)键重启**来源3DS**，运行Hourglass9
4. 进入“SysNAND Backup/Restore”选项，从`NANDmin.bin`恢复SysNAND（在进行系统转移之前做的备份）
1. 如果在**目标3DS**上没有看到任何游戏，将**目标3DS**与你买游戏用的NNID绑定，尝试重新下载该游戏
  + 你可能需要先从"System Settings（系统设置）" - "Data Management（数据管理）"中先将该游戏删除
  + 如果**目标3DS**不是最新版本的操作系统，你可能需要运行ctr-httpwn才能访问eShop
2. 在**来源3DS**上，执行存档和".app"注入步骤（do the the save（and `.app` if you are using the `.app` page）injection steps）
3. 在**来源3DS**上，依次进入"System Settings（系统设置）" - "Data Management（数据管理）" - "DSiWare"，将你的DSiWare游戏复制到SD卡上
4. 将**来源3DS**的SD卡插入**目标3DS**；或者将**目标3DS**SD上的`Nintendo 3DS`文件夹重命名，然后将**来源3DS**SD卡上的`Nintendo 3DS`文件夹复制到**目标3DS**的SD卡上
5. 在**目标3DS**上，依次进入"System Settings（系统设置）" - "Data Management（数据管理）" - "DSiWare"，将DSiWare游戏复制回系统
6. 将SD卡复原，继续进行DSiWare降级

## <a name="ts_d9_backup" />Decrypt9或Hourglass9不能恢复/找不到我的NAND备份

1. 确保你的SD卡**根目录**没有名叫"Decrypt9"的文件夹
3. 尝试使用[H2testw (Windows)](h2testw-(windows)), [F3 (Linux)](f3-(linux))，或[F3X (Mac)](f3x-(mac))检查你的SD卡的错误
4. 尝试备份你的SD卡文件，格式化SD卡并把文件拷贝回去
5. 换一张SD卡

## <a name="ts_sys_down" />启动到SysNAND黑屏

1. 尝试将SD卡拿出后启动系统，启动完成后将SD卡插回。
   1. 长按电源键关闭你的3DS。
   2. 拔出你的SD卡。
   3. 启动3DS。
   4. 桌面菜单出现后，插回SD卡。
   5. 如果这么做问题解决，你需要进入SD卡的`/Nintendo 3DS/(32位ID)/(32位ID)/extdata/00000000/`目录以清除主界面菜单的extdata
    + 欧版：删除 `00000098` 
    + 日版：删除 `00000082`
    + 美版：删除 `0000008f`
    + 神游：删除 `000000A1`
    + 韩版：删除 `000000A9`
    + 台版：删除 `000000B1`
1. 尝试拔掉卡带（包括闪存卡带）开机
2. 如果你可以hardmod（硬改），并且有NAND备份，尝试将NAND备份写入SysNAND。
3. 尝试启动到恢复模式并升级你的系统 
   *老3DS降级到2.1.0的系统后，该方法很可能会失效。*    
   **新3DS降级到2.1.0后，尝试该方法会变砖。**
   1. 长按电源键关闭你的3DS。
   2. 按住L+R+A+Up键的同时，按下电源键开机。
   4. 如果进入安全模式，*仅当你有最新固件版本进入HBL的方法，并且能进行降级的情况下*，才升级你的3DS，并再次尝试降级。
4. 你的3DS可能变砖了。请在[GitHub Issues](https://github.com/majia67/3DS-ARM9LoaderHax-Guide/issues)中提问，或者参考[FAQ](faq#faq_support)页面获取帮助。

## <a name="ts_sys_a9lh" />安装完arm9loaderhax后启动到SysNAND黑屏

1. 确保你有一个正常工作的payload
   1. 检查你的SD卡根目录有`arm9loaderhax.bin`文件。
2. 尝试重置Luma3DS的设置
   1. 删除SD卡上的`/luma/config.bin`文件
   2. 启动Luma3DS后重新设置
3. 尝试启动Hourglass9
   1. 在启动到Luma3DS时按住Start键
4. 尝试删除桌面菜单的extdata
    1. 定位到sd卡的`/Nintendo 3DS/(32位ID)/(32位ID)/extdata/00000000/`
        + 欧版: 删除 `00000098`
        + 日版: 删除 `00000082`
        + 美版: 删除 `0000008f`
        + 神游: 删除 `000000A1`
        + 韩版: 删除 `000000A9`
        + 台版: 删除 `000000B1`
5. 尝试拔掉卡带（包括闪存卡带）开机
7. 尝试这个[测试版payload](https://mega.nz/#!YxMiGDhB!VZLv2XPSqFFzEhf4kGMXAdQtSpIGvnp2vu2W1j4o7cc/) .
   1. 将SD卡根目录的`arm9loaderhax.bin`文件重命名（如果有该文件的话）。
   2. 将新下载的`arm9loaderhax.bin`拷贝到你的SD卡根目录。
   3. 将SD卡插回3DS，按下电源键开机。
   4. 按(A)键。你的3DS应该会关机。这表示arm9loaderhax能正常工作，其它文件有损坏。你的机器**没有**变砖。
8. 如果你以前用Gateway降过级，确保你使用的是最新版的Luma3DS（版本号在v6.2.3及以上）
9. 如果你的系统版本在3.0.0到4.5.0之间，进行如下操作：
   + 确保你使用的是最新版的Luma3DS（版本号在v6.6及以上）
   + 下载[这个文件](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/00000056)并重命名为`firmware.bin`
   + 下载[这个文件](http://nus.cdn.c.shop.nintendowifi.net/ccs/download/0004013800000002/cetk)
   + 复制`firmware.bin`和`cetk`到SD卡的`/luma/`文件夹下
   + 在你的3DS升级完成后，删除这两个文件
9. 尝试按照[9.2.0 ctr迁移](9.2.0-ctrtransfer)进行操作
10. 请在[GitHub Issues](https://github.com/majia67/3DS-ARM9LoaderHax-Guide/issues)中提问，或者参考[FAQ](faq#faq_support)页面获取帮助。

## <a name="ts_sys_blue" />启动时蓝屏（bootrom错误）

1. 你的3DS已变砖。
2. 你需要[硬改](https://gbatemp.net/threads/414498/)或维修/更换你的机器。
