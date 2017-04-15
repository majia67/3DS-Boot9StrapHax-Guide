---
title: "自制程序启动器（声音破解）"
permalink: /homebrew-launcher-(soundhax).html
lang: zh_CN
ref: homebrew-launcher-(soundhax)
---

Homebrew Launcher（自制程序启动器，HBL）有很多进入或启动方法。
{: .notice}

声音破解（SoundHax）支持欧版、日版、韩版和美版，系统版本9.0.0至11.3.0的机器。
{: .notice--info}

确保你的机器的无线传输（就是Wifi）开关是开启的，因为udsploit（下一步要用到）需要无线模块开启才能生效，且部分机器（新3DS和2DS）不能在自制程序启动器中修改无线传输设置。无线传输设置只要开启就行，无需连接到热点（access point）。
{: .notice--info}

卡带升级只会更新系统核心组件，如系统设置，桌面菜单，等等。卡带升级不会更新任天堂3DS声音（Nintendo 3DS Sound）和网络相关的组件，如系统迁移，互联网浏览器，StreetPass Mii Plaza，和eShop。
{: .notice--info}

这意味着从系统版本9.0.0以下进行卡带升级会破坏[Soundhax](homebrew-launcher-(soundhax))！你需要一个[替代方法](homebrew-launcher-(alternatives))进入自制程序启动器！
{: .notice--warning}

#### 你需要

+ 自制程序[新手包](http://smealum.github.io/ninjhax2/starter.zip)
+ 最新版的[SoundHax](http://soundhax.com/) *依照你的设备和区域选择对应的文件下载*
+ The [otherapp payload](https://smealum.github.io/3ds/#otherapp) *依照你的设备和区域选择对应的文件下载*

#### 操作指南

1. 关机
1. 将SD卡取下，插入电脑
1. 解压缩`starter.zip`，将`starter`文件夹下的所有文件拷贝到SD卡的根目录中
1. 将SoundHax的`.m4a`文件拷贝到SD卡的根目录中
1. 将the otherapp payload拷贝到SD卡的根目录中，并重命名为`otherapp.bin`
1. 将SD卡插回设备
1. 开机
1. 运行Nintendo 3DS Sound（任天堂3DS声音）
1. 跳过所有的小鸟提示，正常关闭程序，再重新打开它
  + 如果立刻运行SoundHax，会造成每次打开Nintendo 3DS Sound都会有小鸟提示
1. 进入`/SDCARD`目录，播放"<3 nedwill 2016"
  + 可能需要试很多次
  + 如果画面卡住了，长按电源键强制关机，然后再试一次
1. 你的3DS应该开始加载自制程序启动器了

---

下一步请进入[SafeCTRTransfer（自制程序启动器）](safectrtransfer-(homebrew-launcher))
{: .notice--primary}
