---
title: "DSiWare降级（存档注入）"
permalink: /dsiware-downgrade-(save-injection).html
lang: zh_CN
ref: dsiware-downgrade-(save-injection)
---

如果你的系统版本是11.0.0或11.1.0，你必须参照本节教程，使用DSiWare降级你的NATIVE_FIRM
{: .notice}

本方法利用了一个设计上的缺陷，能让DSiWare titles在NAND的任意位置进行读写。
{: .notice--info}

做好准备等20分钟（新3DS）至一小时（老3DS）。Slowhax (waithax) 的名字不是白起的（译者注：slowhax意即'慢破解'，是英文教程作者的一个调侃）。
{: .notice--info}

本方法是"FIRM partitions known-plaintext"漏洞的一种目前有效的实现。详情参见[这里](https://www.3dbrew.org/wiki/3DS_System_Flaws)。
{: .notice--info}

你的DSiWare的存档在被替换为破解存档前会进行备份。
{: .notice--info}

#### 你需要

* 你的3DS上已经拥有（并且已经安装了）以下可以破解的DSiWare游戏中的一个*（你必须已经安装过它们。它们都已经在eShop上被下架）*
  + **Fieldrunners**
  + **Legends of Exidia**
  + **Guitar Rock Tour**  
  + **The Legend of Zelda: Four Swords (Anniversary Edition)**  
* 自制程序启动器进入点，参见[自制程序启动器（声音破解）](homebrew-launcher-(soundhax))或[自制程序启动器（无浏览器）](homebrew-launcher-(no-browser))
* [`4B51394A.zip`](images/4B51394A.zip)
* 最新版的[3ds_dsiwarehax_installer](https://github.com/yellows8/3ds_dsiwarehax_installer/releases/latest)
* 最新版的[waithax](https://github.com/Mrrraou/waithax/releases/latest)
* 最新版的[3DSident](https://github.com/joel16/3DSident/releases/latest)
* 最新版的[dgTool](https://github.com/Plailect/dgTool/releases/latest)
* 自制程序[新手包](http://smealum.github.io/ninjhax2/starter.zip)
* 适合你3DS版本的NFIRM压缩包
  + [新3DS 11.0.0](magnet:?xt=urn:btih:2d13a5ea1570f911bd5c6423e0c30e51d548837a&dn=11.0.0%5Fto%5F10.4.0%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  + [老3DS 11.0.0](magnet:?xt=urn:btih:72393bbd99bc285db84a9cabf39d9b3200058d6a&dn=11.0.0%5Fto%5F10.4.0%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  ~    
  + [新3DS 11.1.0](magnet:?xt=urn:btih:d7d60c27c18f53bd8508a194656a465f6448bedf&dn=11.1.0%5Fto%5F10.4.0%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  + [老3DS 11.1.0](magnet:?xt=urn:btih:0caf9a948a2d8bf23606d641f6628e2baeb983bb&dn=11.1.0%5Fto%5F10.4.0%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     

#### 操作指南

##### 第一部分 - 准备工作

1. 解压缩`starter.zip`压缩包，复制其中的文件到你的SD卡根目录，覆盖已有文件
  + 这将确保自制程序启动器是最新版本；老版本会造成运行3ds_dsiwarehax_installer的时候卡死
4. 解压缩3ds_dsiwarehax_installer的压缩包，复制`3ds`文件夹，并覆盖到你的SD卡根目录下
4. 解压缩`4B51394A.zip`压缩包，复制`4B51394A`文件夹到你SD卡的`/3ds/3ds_dsiwarehax_installer/dsiware/`目录下
5. 解压缩3DSident压缩包，复制其中的`3ds`文件夹，与你**目标3DS**SD卡上的对应文件夹合并。
5. 复制`waithax.3dsx`到你SD卡的`/3ds/`文件夹下
6. 复制dgTool的`boot.nds`文件到你的SD卡根目录下
1. 在SD卡根目录新建一个名为`dgTool`的文件夹，如果它还不存在的话
3. 解压缩NFIRM的压缩包，复制文件到SD卡的`dgTool`文件夹下
4. 将SD卡插回你的3DS

##### 第二部分 - 备份DSiWare

完成整个教程后，你可以通过从系统内存中删除DSiWare，再从SD卡中恢复备份文件，恢复你的DSiWare存档
{: .notice--info}

备份文件仅能用于当前的NAND。如果你格式化了你的3DS，或者从NAND备份中恢复（特别是如果`movable.sed`曾被修改过），它将不再可用。
{: .notice--info}

1. 进入系统设置，选择"Data Management"（数据管理），然后选"DSiWare"
3. 将你想使用的DSiWare游戏复制到SD卡
4. 退出系统设置

##### 第三部分 - waithax

1. 使用你的进入点，进入自制程序启动器
2. 运行waithax
3. 等待
  + 在新3DS上，大概要花20分钟的时间（由于某个bug，在某些系统上可能会花和老3DS同样长的时间）
  + 在老3DS上，大概要花一个小时的时间
4. 完成后，按(Start)键退出
5. 运行3ds_dsiwarehax_installer
6. 选择你想安装漏洞的DSiWare游戏
7. 完成后，按(A)键退出
8. 按(Start)键打开自制程序启动器的退出菜单
9. 按(A)键退出

##### 第四部分 - 备份NFIRM

3. 运行你的DSiWare游戏
4. 开始你的DSiWare游戏，运行dgTool
  + **Fieldrunners**：点击主菜单的'Scores'（得分）按钮
  + **Legends of Exidia**：在两个标题界面按(A)键或(Start)键，选择第一个存档并点继续
  + **Guitar Rock Tour**: 将页面下拉，依次进入High-Scores（高分榜） -> Drums（鼓） -> Easy（简单）
  + **The Legend of Zelda: Four Swords (Anniversary Edition)**：开始游戏
  + 如果你的游戏没有安装上破解的存档文件，请从头开始（译者注：这里不太确定，应该是重启一次游戏再试，或者从第三部分运行3ds_dsiwarehax_installer处开始再装一次破解存档，而不是从教程开头开始）
5. 选择"Dump f0f1"，备份你的NFIRM
  + 这一步需要一些时间
6. 记下NFIRM的备份位置
7. 退出dgTool
  + 你可能需要按电源键强制关机
8. 将SD卡插回你的电脑，复制`F0F1_N3DS.bin`或`F0F1_O3DS.bin`（取决于你的设备）到一个安全的地方
  + 在多个位置进行备份
  + 备份文件可以在将来出现错误时将你的机器救砖

##### 第五部分 - 刷入NFIRM

**永远不要在一个已经安装了arm9loaderhax的设备上使用dgTool进行降级，否则你的设备将变砖！**
{: .notice--danger}

1. 运行你的DSiWare游戏
2. 开始你的DSiWare游戏，运行dgTool
  + **Fieldrunners**：点击主菜单的'Scores'（得分）按钮
  + **Legends of Exidia**：在两个标题界面按(A)键或(Start)键，选择第一个存档并点继续
  + **Guitar Rock Tour**: 将页面下拉，依次进入High-Scores（高分榜） -> Drums（鼓） -> Easy（简单）
  + **The Legend of Zelda: Four Swords (Anniversary Edition)**：开始游戏
3. 选择"Downgrade FIRM to 10.4"并确认，将10.4.0 NFIRM bin刷入**目标3DS**
4. 退出dgTool
  + 你可能需要按电源键强制关机
5. 重启

##### 第六部分 - Exploit verification

2. 将SD卡插回3DS
3. 使用你的进入点，进入自制程序启动器
4. 运行3DSident
5. 验证以下信息是否正确：
  + **Kernel version（内核版本）**: 2.50-11
  + **FIRM version（固件版本）**: 2.50-11
  + 如果其中任何一个没有显示如上所示的版本号，确保你使用的是正确的NFIRM压缩包，然后尝试重新刷入NFIRM

你的设备在系统设置中的版本号*不会*变更。
{: .notice--info}

进入[Decrypt9（自制程序启动器）](decrypt9-(homebrew-launcher))继续教程
{: .notice--primary}
