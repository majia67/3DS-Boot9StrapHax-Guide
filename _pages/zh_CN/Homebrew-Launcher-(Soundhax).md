---
title: "自制程序启动器（声音破解）"
---

Homebrew Launcher（自制程序启动器，HBL）有很多进入或启动方法。
{: .notice--info}

声音破解（SoundHax）支持欧版、日版、韩版和美版，系统版本9.0.0至11.3.0的机器。
{: .notice--info}

确保你的机器的无线传输（就是Wifi）开关是开启的，因为udsploit（下一步要用到）需要无线模块开启才能生效，且部分机器（新3DS和2DS）不能在自制程序启动器中修改无线传输设置。无线传输设置只要开启就行，无需连接到热点（access point）。
{: .notice--info}

{% capture notice-1 %}
卡带升级只会更新系统核心组件，如系统设置，桌面菜单，等等。卡带升级不会更新任天堂3DS声音（Nintendo 3DS Sound）和网络相关的组件，如系统迁移，互联网浏览器，StreetPass Mii Plaza，和eShop。
<br><br>
这意味着从一个带有旧版任天堂3DS声音的系统（老3DS欧版、日版、韩版或美版，系统版本在7.0.0以下）卡带升级到一个带有新版任天堂3DS声音的系统会破坏[Soundhax](homebrew-launcher-(soundhax))！你需要一个[替代方法](homebrew-launcher-(alternatives))进入自制程序启动器！
{% endcapture %}

<div class="notice--warning">{{ notice-1 | markdownify }}</div>

#### 你需要

* 自制程序[新手包](http://smealum.github.io/ninjhax2/starter.zip)
* 最新版的[SoundHax](http://soundhax.com/) *依照你的设备和区域选择对应的文件下载*
* The [otherapp payload](https://smealum.github.io/3ds/#otherapp) *依照你的设备和区域选择对应的文件下载*

#### 操作指南

1. 关机
1. 将SD卡取下，插入电脑
1. 解压缩`starter.zip`，将`starter`文件夹*里面*的所有文件拷贝到SD卡的根目录中
1. 将SoundHax的`.m4a`文件拷贝到SD卡的根目录中
1. 将the otherapp payload拷贝到SD卡的根目录中，并重命名为`otherapp.bin`

    ![]({{ base_path }}/images/screenshots/soundhax-file-layout.png)
    {: .notice--info}

1. 将SD卡插回设备
1. 开机
1. 运行Nintendo 3DS Sound（任天堂3DS声音）

    ![]({{ base_path }}/images/screenshots/soundhax-welcome.png)
    {: .notice--info}

1. 如果你之前从未打开过Nintendo 3DS Sound，然后出现了一只小鸟提示你如何使用，请过完所有的提示，正常关闭程序，然后重新打开
  + 如果不过完提示就立刻运行SoundHax，会造成每次打开Nintendo 3DS Sound都会有小鸟提示
1. 进入`/SDCARD`目录，播放"<3 nedwill 2016"
  + 可能需要试很多次
  + 如果画面卡住了，长按电源键强制关机，然后再试一次
  + 如果出现红屏，确保你是复制了`starter`文件夹*里面*的所有文件到SD卡根目录，而不是`starter`文件夹本身

    ![]({{ base_path }}/images/screenshots/soundhax-launch.png)
    {: .notice--info}

1. 你的3DS应该开始加载自制程序启动器了

    ![]({{ base_path }}/images/screenshots/homebrew-launcher.png)
    {: .notice--info}


---

下一步请进入[安装boot9strap（自制程序启动器）](installing-boot9strap-(homebrew-launcher))
{: .notice--primary}
