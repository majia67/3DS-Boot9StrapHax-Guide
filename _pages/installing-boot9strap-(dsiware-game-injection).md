---
title: "安装boot9strap（DSiWare游戏注入）"
---

请注意：某些版本的Luma3DS只会在检测到多于一个payload时显示Luma3DS启动器菜单。如果只检测到一个payload，按住(Start)键启动将直接运行GodMode9。
{: .notice--info}

**你需要一个能进行BT下载的软件，如[Deluge](http://dev.deluge-torrent.org/wiki/Download)、[aria2](https://aria2.github.io/)或迅雷，才能下载本节教程中的[磁力链接](http://baike.baidu.com/item/%E7%A3%81%E5%8A%9B%E9%93%BE%E6%8E%A5)。**
{: .notice--success}

在开始之前，确保你已经阅读了[安装boot9strap (DSiWare)](installing-boot9strap-(dsiware))页面中所有的注意和警告事项。
{: .notice--danger}

#### 你需要

* 两台3DS
  + **来源3DS**：运行*最新系统版本*自制固件（boot9strap和arm9loaderhax）的3DS
  + **目标3DS**：运行原生系统的3DS（版本为*11.4.0*）
* **来源3DS**上已经购买（或原来就有）并安装了一个eShop版的DSiWare游戏
  + 盗版游戏**不能**用来破解
  + 参见[安装boot9strap（DSiWare可注入游戏列表）](installing-boot9strap-(dsiware-game-injection-list))页面查看合适的游戏
* 对应你的区域的sudokuhax注入包
  + 美版：[`DSiWare_usa_sudokuhax_injection.zip`](magnet:?xt=urn:btih:7ed7fee15c900ed02b5e2cb3c8e7a0363f4d9354&dn=DSiWare_usa_sudokuhax_injection.zip&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce)
  + 欧版: + [`DSiWare_eur_sudokuhax_injection.zip`](magnet:?xt=urn:btih:1542dd3c2bf7785b1e7a6dda3887fc8fb2710685&dn=DSiWare_eur_sudokuhax_injection.zip&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce)
  + 日版：[`DSiWare_jpn_4swordshax_injection.zip`](magnet:?xt=urn:btih:1bcc90c93da91c9876671f6218084207def90db9&dn=DSiWare_jpn_4swordshax_injection.zip&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce)
* 最新版的[GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* 最新版的[b9sTool](https://github.com/Plailect/b9sTool/releases/latest)
* 最新版的[boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *（标准版boot9strap；不是`devkit`或`ntr`版）*
* 最新版的[Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *（`.7z`压缩包）*
* 自制程序[新手包](http://smealum.github.io/ninjhax2/starter.zip)
* 对应**目标3DS**的11.4.0 `.firm`文件
  + 老3DS：[`2.54-0_11.4_OLD.firm`](magnet:?xt=urn:btih:0dd89d42ad711f770da899af05ee162ede0d0070&dn=2.54-0_11.4_OLD.firm&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  + 新3DS：[`2.54-0_11.4_NEW.firm`](magnet:?xt=urn:btih:3b59dd43eec3edb133555f58d1180bfb196acbb4&dn=2.54-0_11.4_NEW.firm&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)

#### 操作指南

##### 第一部分 - 准备工作

使用一个[存档管理器](https://github.com/J-D-K/JKSM/releases/latest)，备份目标3DS上（它会被格式化！）你觉得重要的存档。
{: .notice--warning}

1. 将**来源3DS**关机
1. 将**来源3DS**的SD卡插入电脑中
1. 解压GodMode9 `.zip`压缩包，复制`GodMode9.firm`文件（arm9loaderhax用户选择`GodMode9.bin`文件）到**来源3DS**SD卡的`/luma/payloads/`目录下
1. 解压缩DSiWare注入包，复制`.app`文件到**来源3DS**的SD卡根目录
1. 复制DSiWare注入包中的`savedata`文件夹到**来源3DS**的SD卡根目录下
1. 将**来源3DS**的SD卡插回
1. 按住(Start)键启动**来源3DS**，运行Luma3DS启动器菜单
1. 按(A)键运行GodMode9
1. 按(Home)键调出行动菜单
1. 选择"More..."
1. 选择"Backup NAND"
1. 按(A)键继续
1. 按住(R)键的同时按(B)键，弹出SD卡，并插入电脑
1. 将**目标3DS**的SD卡取出，并插入电脑
1. **将两台3DS的SD卡上的文件备份到电脑上两个单独的文件夹中（区分清楚哪个文件夹对应哪台3DS）！**
1. 将两张SD卡分别插回对应的3DS中
1. 在**来源3DS**上按(Start)键，重启机器

##### 第二部分 - 注入游戏和存档

1. 按住(Start)键启动**来源3DS**，运行Luma3DS启动器菜单
1. 按(A)键运行GodMode9
1. 进入`SDCARD`
1. 移动光标到DSiWare注入`.app`文件上，按(Y)键复制它
1. 按(B)键返回主菜单
1. 依次进入`SYSNAND TWLN` -> `title` -> `00030004` -> `(8 Character ID)`（8位字符串ID）
  + 8位字符串ID参见[安装boot9strap（DSiWare可注入游戏列表）](installing-boot9strap-(dsiware-game-injection-list))页面
1. 进入`content`
1. 移动光标到目录下面的`.app`文件上，按(A)键
1. 选择"Inject data @offset"（在位移处注入数据）
1. 按(A)键选择offset（位移）`00000000`
1. 按(A)键确定解锁SysNAND写入，输入屏幕提示的组合键
1. 按(B)键返回到主菜单
1. 依次进入`SYSNAND TWLN` -> `title` -> `00030004` -> `(8 Character ID)`（8位字符串ID）
  + 8位字符串ID参见[安装boot9strap（DSiWare可注入游戏列表）](installing-boot9strap-(dsiware-game-injection-list))页面
1. 进入`data`
1. 移动光标到`public.sav`文件上，按(A)键
1. 选择"Mount as FAT image"（作为FAT镜像加载）
1. 按(B)键返回到主菜单
1. 选择`SDCARD`
1. 在`savedata`文件夹中的文件上按(Y)键复制它们
  + 如果在`savedata`文件夹里还有一个`savedata`文件夹，这不是错误。你应该复制第二个`savedata`文件夹，而不是里面的文件
1. 按(B)键返回主菜单
1. 选择`FAT IMAGE`
1. 按(X)键删除`FAT IMAGE`里面的所有文件
1. 按(Y)键，将`savedata`文件夹**里面的文件**复制到`FAT IMAGE`下
1. 选择"Copy path(s)"
1. 按(A)键解锁镜像写保护，输入屏幕提示的组合键
1. 按(Start)键重启
1. 在**来源3DS**上运行你的DSiWare游戏
1. 点击屏幕或按任意键开始游戏，测试游戏存档是否有效
  + 如果你的游戏报有关`boot.nds`的错误，说明**漏洞已被成功利用**
  + 如果你的游戏报错提示存档损坏或不能访问，请确认你复制的是`savedata`文件夹**里面的文件**，而非`savedata`文件夹本身
  + 如果你的游戏正常进行，没有报有关`boot.nds`的错误，你应该立刻停止，找一下哪里出了问题
  + 如果出现黑屏，[参见这个问题排查](troubleshooting#twl_broken)
  + 如果在**目标3DS**上没有这个游戏，或报错提示存档损坏或不能访问，[参见这个问题排查](troubleshooting#ts_dsiware)

##### 第三部分 - 系统迁移

1. **将两台3DS的SD卡上的所有文件分别备份到电脑上两个分开的文件夹中（标记好哪个是哪个！）**
1. 将两张SD卡插回各自对应的3DS
1. 如果**目标3DS**上已经登录了任天堂网络ID（NNID），你必须在系统设置里面格式化设备：
  + 选择"Other Settings"（其它设置）里面的最后一页，选择"Format System Memory"（格式化系统内存），然后按提示操作
1. 请阅读以下注意事项：
  + 你的自制系统的3DS = 来源3DS = "Source System"（来源系统）
  + 你的原生系统3DS = 目标3DS = "Target System"（目标系统）
  + **如果提示，请迁移DSiWare titles！**
  + 如果提示，**不要**删除来源系统上的SD内容
  + 确保在进行系统转移的时候，两台3DS的电池都有电
  + 仅限2DS/老3DS（来源）转移到新3DS（目标）- 如果被问到使用何种方式转移SD卡上的数据：
    + **不要**选择"Low-Capacity microSD Card Transfer"（低容量microSD卡迁移）或minimal option（最小迁移，选项2），因为这将只转移tickets，可能不会转移DSiWare的存档。
    + 快速的方法：如果你能自己将来源SD卡的数据移动到目标SD卡，当提示时选择"PC-Based Transfer"（电脑端迁移，选项3）。
    + 最慢的方法：如果你不能自己在电脑上迁移SD卡数据，选择**full** "Wireless Transfer"（完整无线迁移，选项1）。
1. 进入[这个链接](http://en-americas-support.nintendo.com/app/answers/detail/a_id/227/)，按照任天堂的官方操作指南进行系统迁移。记住你刚才读的注意事项。

##### 第四部分 - 恢复来源3DS

1. 在**来源3DS**上，完成初始化的操作
2. 在下面的操作中选择一个执行：
    + 在**目标3DS**上完成本教程剩下的部分，然后等一个礼拜，再从**目标3DS**迁移回**来源3DS** *（请记住，你不能从一个新3DS迁移回一个老3DS）*
    + 给任天堂打电话，告诉它们你访问不了你当前NNID绑定的设备（也就是**目标3DS**），想把它绑到另一台设备上（也就是**来源3DS**）（译者注：真是对大陆玩家的实力嘲讽）
    + 你也可以参照[移除NNID](https://3ds.guide/troubleshooting#rm_nnid) 页面，移除**来源3DS**上的NNID，如果你希望它留在**目标3DS**上
1. 按住(Start)键重启**来源3DS**，运行Luma3DS启动器菜单
1. 按(A)键运行GodMode9
1. 进入`[0:] SDCARD`
1. 移动光标到你的NAND `.bin`文件上，按(A)键选中，然后选择"NAND image options..."，然后选择"Restore SysNAND (safe)"
1. 按(A)键解锁SysNAND写保护，然后输入提示的按键组合
  + 这不会覆盖已经安装的boot9strap
1. 输入提示的按键组合，解锁SysNAND (lvl1)写保护
  + 这可能需要一些时间
1. 完成后，按(A)键继续
1. 按(Start)键重启**来源3DS**

##### 第五部分 - 备份目标3DS的FIRM

1. 解压Luma3DS`.7z`压缩包，复制`boot.firm`文件到你SD卡的根目录
1. 复制`boot.nds`文件到**目标3DS**的SD根目录
1. 解压缩`starter.zip`压缩包，复制`starter`文件夹下的所有文件和文件夹到**目标3DS**的SD卡根目录
1. 在**目标3DS**的SD卡根目录新建一个名为`boot9strap`的文件夹
1. 复制对应**目标3DS**的11.4.0 `.firm`文件到**目标3DS**的SD卡的`boot9strap`目录下
1. 解压缩boot9strap `.zip`压缩包，复制`boot9strap.firm`文件到**目标3DS**的SD卡的`/boot9strap/`目录下
1. 在**目标3DS**上运行你的DSiWare游戏，启动b9sTool
  + 如果你的游戏没有运行b9sTool，[参见这个问题排查](troubleshooting#ts_dsiware)
1. 选择"Dump F0F1"，备份**目标3DS**的FIRM
1. 记下FIRM的备份位置
1. 退出b9sTool
  + 你可能需要按电源键强制关机
1. 将SD卡插回你的电脑，复制`F0F1_N3DS.bin`或`F0F1_O3DS.bin`（取决于你的机器型号）到一个安全的地方
  + 在多个位置进行备份
  + 备份文件可以在将来出现错误时将你的机器救砖
1. 将SD卡插回**目标3DS**

##### 第六部分 - 刷入目标3DS的FIRM

**不要在已经安装了arm9loaderhax的设备上使用b9sTool，否则你的设备将变砖！**
{: .notice--danger}

1. 在**目标3DS**上运行你的DSiWare游戏，进入b9sTool
1. 选择"Install boot9strap"并确认
1. 退出b9sTool，然后关机
  + 你可能需要按电源键强制关机
1. 开机（**目标3DS**）

##### 第七部分 - 设置Luma3DS

1. 你的机器应该启动到了Luma3DS启动器菜单
  + 如果黑屏，[参见这个问题排查](troubleshooting#ts_sys_b9s)
1. 通过方向键和A键来启用以下设置：
  + **"Show NAND or user string in System Settings"**
1. 按下(Start)键保存设置并重启
  + 如果出现错误，请继续进行接下来的教程

___

继续进行[收尾工作](finalizing-setup)
{: .notice--primary}
