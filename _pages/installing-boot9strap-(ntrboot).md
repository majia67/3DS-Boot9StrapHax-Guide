---
title: "安装boot9strap（ntrboot）"
---

### 教程须知

本页面包含[磁力链](https://en.wikipedia.org/wiki/Magnet_URI_scheme)，你需要一个类似[Deluge](http://dev.deluge-torrent.org/wiki/Download)的客户端才能下载该链接的文件。（译者注：迅雷也可以）

想解压缩本页面中的`.7z`文件，你需要一个压缩文件管理器，例如[7-Zip](http://www.7-zip.org/)或者[The Unarchiver](https://theunarchiver.com/)。（译者注：国内常用的WinRAR也是支持`.7z`文件解压缩的）

### 你需要

* 一块能让你的机器进入休眠模式的磁铁（如果使用的是折叠的机器）
* 已经刷入ntrboot的烧录卡
* 最新版本的[SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest){:target="_blank"}
* 最新版本的[boot9strap](https://github.com/SciresM/boot9strap/releases/latest){:target="_blank"} *（标准版boot9strap；不是`devkit`或`ntr`版）*
* 最新版本的[Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest){:target="_blank"} *(the `.7z` file)*
* 最新版本的[the Homebrew Launcher](https://github.com/fincs/new-hbmenu/releases/latest){:target="_blank"}

### 操作指南

#### 第一部分 - 准备工作

1. 关机
1. 将SD卡插入电脑
  + 注意这里是你的3DS的SD卡，*不是*你的烧录卡上的SD卡
1. 复制`SafeB9SInstaller.firm`文件到SD卡根目录，并重命名为`boot.firm`
1. 复制`boot.3dsx`文件到SD卡根目录
1. 在SD卡根目录创建名为`boot9strap`的文件夹
1. 解压缩boot9strap`.zip`压缩包，将`boot9strap.firm`和`boot9strap.firm.sha`文件复制到SD卡的`/boot9strap/`目录下

    ![]({{ "/images/screenshots/boot9strap-ntrboot-file-layout.png" | absolute_url }})
    {: .notice--info}

1. 将SD卡重新插回机器
1. 开机

#### 第二部分 - ntrboot

1. 用磁铁在你的机器上寻找触发休眠模式感应器的位置
  + 老2DS上不需要这一步（因为自带休眠模式的开关）
1. 关机
1. 将烧录卡插入机器
1. 用磁铁触发睡眠模式
  + 老2DS则应该开启睡眠模式
1. 同时按住(Start) + (Select) + (X) + (Power)键数秒，然后松开按键
  + 可能需要多试几次才能成功，因为这几个按键的位置很尴尬
1. 如果漏洞利用成功，你的机器会启动SafeB9SInstaller

#### 第三部分 - 安装boot9strap

1. 等待所有安全检查完成
1. 拿开磁铁
  + 老2DS则应该关闭休眠模式
1. 按照提示输入按键组合，安装boot9strap
1. 完成后，按住电源键强制关机
  + 你的机器只有在完成了下一部分操作后才能启动到SafeB9SInstaller的界面

#### 第四部分 - 设置Luma3DS

1. 将机器上的SD卡取下，插入电脑
1. 删除SD卡根目录的`boot.firm`文件
1. 解压缩Luma3DS`.7z`压缩包，将`boot.firm`文件复制到SD卡的根目录下
1. 将SD卡插回机器
1. 开机
1. 你的机器应该启动到了Luma3DS启动器菜单
  + 如果黑屏，[参见这个问题排查](troubleshooting#black-screen-on-sysnand-boot-after-installing-boot9strap)
1. 通过方向键和(A)键来启用以下设置：
  + **"Show NAND or user string in System Settings"**
1. 按下(Start)键保存设置并重启
  + 如果出现错误，请继续进行接下来的教程

___

### 继续进行[收尾工作](finalizing-setup)
{: .notice--primary}

___

接下来的教程不是必须要做的。它能将你的烧录卡还原到初始状态（使用正常的功能）。

注意Acekard 2i烧录卡在安装了ntrboot破解之后仍然能运行`.nds`文件，但仅适用于NDS或安装了自制系统的3DS，而不适用于DSi或原版3DS系统。

仅当完成了本节前面所有教程后才能执行下面的操作。

#### 第五部分 - 移除ntrboot

##### 你需要

* 最新版本的[ntrboot_flasher](https://github.com/ntrteam/ntrboot_flasher/releases/latest){:target="_blank"}
* 针对你烧录卡的内核文件
  + 注意如果你按照"刷入ntrboot（3DS多系统）"执行了教程，内核文件已经在正确的位置，不需要再下载
  + 如果你不知道你的烧录卡对应哪个硬件修正版（HW Revision），把每个都试一下。只有正确的版本会让你的烧录卡从桌面菜单正常启动，但是错误的版本不会使你的烧录卡变砖。

| 烧录卡 | 硬件修正版本号 | 内核文件 |
|-|:-:|:-:|
| **Ace3DS X** | | *无* |
| **Acekard 2i** | HW 81 | <i class="fa fa-magnet" aria-hidden="true" title="这是一个磁力链，请使用BT种子客户端下载。"></i> - [Acekard_2i_(HW_81)-Flashrom.zip](magnet:?xt=urn:btih:71ce385a1d65e28719c419fe58d171a4873501ff&dn=Acekard%5F2i%5F%28HW%5F81%29-Flashrom.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce) |
| **Acekard 2i** | HW 44 | <i class="fa fa-magnet" aria-hidden="true" title="这是一个磁力链，请使用BT种子客户端下载。"></i> - [Acekard_2i_(HW_44)-Flashrom.zip](magnet:?xt=urn:btih:d04bd19e15bf8600ccef6540bdbd043846888132&dn=Acekard%5F2i%5F%28HW%5F44%29-Flashrom.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce) |
| **DSTT** | | *暂缺* |
| **Infinity 3 R4i** | HW A5 | <i class="fa fa-magnet" aria-hidden="true" title="这是一个磁力链，请使用BT种子客户端下载。"></i> - [R4i_Gold_3DS_(HW_A5)-Flashrom.zip](magnet:?xt=urn:btih:c6dee8cc9535d58284ccb8430c9af4682c3e1efc&dn=R4i%5FGold%5F3DS%5F%28HW%5FA5%29-Flashrom.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce) |
| **R4 3D Revolution** | HW A6 | <i class="fa fa-magnet" aria-hidden="true" title="这是一个磁力链，请使用BT种子客户端下载。"></i> - [R4i_Gold_3DS_(HW_A6)-Flashrom.zip](magnet:?xt=urn:btih:e1675722834b870ea64ddf1ef9ca77d78db2be00&dn=R4i%5FGold%5F3DS%5F%28HW%5FA6%29-Flashrom.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce) |
| **R4i Gold 3DS Deluxe "Starter"** | | *暂缺* |
| **R4i Gold 3DS** | HW 4 | <i class="fa fa-magnet" aria-hidden="true" title="这是一个磁力链，请使用BT种子客户端下载。"></i> - [R4i_Gold_3DS_(HW_4)-Flashrom.zip](magnet:?xt=urn:btih:a742778ade94b4a0b877cc481ba0f1a4120262da&dn=R4i%5FGold%5F3DS%5F%28HW%5F4%29-Flashrom.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce) |
| **R4i Gold 3DS** | HW 5 | *暂缺* |
| **R4i Gold 3DS** | HW 6 | *暂缺* |
| **R4i Gold 3DS** | HW 7 | *暂缺* |
| **R4i Gold 3DS** | HW 8 | *暂缺* |
| **R4i Gold 3DS Plus** | | *无* |
| **R4i Gold 3DS RTS** | HW A5 | <i class="fa fa-magnet" aria-hidden="true" title="这是一个磁力链，请使用BT种子客户端下载。"></i> - [R4i_Gold_3DS_(HW_A5)-Flashrom.zip](magnet:?xt=urn:btih:c6dee8cc9535d58284ccb8430c9af4682c3e1efc&dn=R4i%5FGold%5F3DS%5F%28HW%5FA5%29-Flashrom.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce) |
| **R4i Gold 3DS RTS** | HW A6 | <i class="fa fa-magnet" aria-hidden="true" title="这是一个磁力链，请使用BT种子客户端下载。"></i> - [R4i_Gold_3DS_(HW_A6)-Flashrom.zip](magnet:?xt=urn:btih:e1675722834b870ea64ddf1ef9ca77d78db2be00&dn=R4i%5FGold%5F3DS%5F%28HW%5FA6%29-Flashrom.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce) |
| **R4i Gold 3DS RTS** | HW A7 | <i class="fa fa-magnet" aria-hidden="true" title="这是一个磁力链，请使用BT种子客户端下载。"></i> - [R4i_Gold_3DS_(HW_A7)-Flashrom.zip](magnet:?xt=urn:btih:d780a1fbcb83d0d3c99748c87534f77957da98ce&dn=R4i%5FGold%5F3DS%5F%28HW%5FA7%29-Flashrom.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce) |
| **R4i Ultra** | | <i class="fa fa-magnet" aria-hidden="true" title="这是一个磁力链，请使用BT种子客户端下载。"></i> - [R4i_Ultra-Flashrom.zip](magnet:?xt=urn:btih:e2a080eb70b92d3127ffea2a5be6bbdb1928a438&dn=R4i%5FUltra-Flashrom.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce) |
| **R4i-SDHC 3DS RTS** | | <i class="fa fa-magnet" aria-hidden="true" title="这是一个磁力链，请使用BT种子客户端下载。"></i> - [R4i-SDHC_3DS_RTS-Flashrom.zip](magnet:?xt=urn:btih:11a4a3b6dd1cef5652b49a413d8e8c662449d819&dn=R4i-SDHC%5F3DS%5FRTS-Flashrom.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce) |
| **R4i-SDHC B9S** | | <i class="fa fa-magnet" aria-hidden="true" title="这是一个磁力链，请使用BT种子客户端下载。"></i> - [R4i-SDHC_3DS_RTS-Flashrom.zip](magnet:?xt=urn:btih:11a4a3b6dd1cef5652b49a413d8e8c662449d819&dn=R4i-SDHC%5F3DS%5FRTS-Flashrom.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce) |
| **R4iSDHC GOLD Pro 20XX**** | | <i class="fa fa-magnet" aria-hidden="true" title="这是一个磁力链，请使用BT种子客户端下载。"></i> - [R4iSDHC_GOLD_Pro_20XX-Flashrom.zip](magnet:?xt=urn:btih:f41aeb6b88a986bb0c5246c53132f3b82052f58b&dn=R4iSDHC%5FGOLD%5FPro%5F20XX-Flashrom.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce) |
| **R4iSDHC RTS LITE 20XX** | | <i class="fa fa-magnet" aria-hidden="true" title="这是一个磁力链，请使用BT种子客户端下载。"></i> - [R4iSDHC_RTS_LITE_20XX-Flashrom.zip](magnet:?xt=urn:btih:543f90f7c50ee847af1d2152bdcbe76e7ed364e4&dn=R4iSDHC%5FRTS%5FLITE%5F20XX-Flashrom.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce) |
| **R4iSDHC Dual-Core 20XX** | | <i class="fa fa-magnet" aria-hidden="true" title="这是一个磁力链，请使用BT种子客户端下载。"></i> - [R4iSDHC_Dual-Core_20XX-Flashrom.zip](magnet:?xt=urn:btih:be5b27b85dcb8a696191a1eddef478f7ab346e06&dn=R4iSDHC%5FDual-Core%5F20XX-Flashrom.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce) |

##### 操作指南

1. 关机
1. 将SD卡取下，插入电脑
  + 注意这里是你的3DS的SD卡，*不是*你的烧录卡上的SD卡
1. 在SD卡上创建名为`ntrboot`的文件夹
1. 解压缩你的烧录卡内核备份`.zip`压缩包，复制`.bin`文件到你的SD卡的`/ntrboot/`目录下
1. 在你的SD卡的`luma`文件夹中创建一个`payloads`文件夹
1. 复制`ntrboot_flasher.firm`文件到SD卡的`/luma/payloads/`目录下
1. 将SD卡插回机器
1. 将烧录卡插入机器
1. 在启动机器时按住(Start)键，启动ntrboot_flasher
1. 阅读屏幕上红色的警告文字
1. 按(A)键继续
1. 选择你的烧录卡
  + 如果你在列表顶端没有看到你的烧录卡，请阅读下屏中针对每个选项的提示信息
1. 选择"Restore Flash"
1. 按(A)键执行
1. 等待操作完成
1. 按(A)键返回到主菜单
1. 按(B)键关机
