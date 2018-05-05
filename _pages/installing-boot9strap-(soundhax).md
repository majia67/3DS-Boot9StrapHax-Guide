---
title: "安装boot9strap (Soundhax)"
---

### 教程须知

如果你的3DS之前已经破解，并安装了基于EmuNAND的自制系统，请务必注意本教程仅适用于SysNAND，教程内的步骤应当应用在你的SysNAND上。注意EmuNAND和RedNAND是[同一概念](http://3dbrew.org/wiki/NAND_Redirection)的两种略微不同的实现。

Soundhax（和pre9otherapp合用）兼容系统版本在4.0.0至8.1.0的欧版、日版、韩版和美版机。

想解压缩本页面中的`.7z`文件，你需要一个压缩文件管理器，例如[7-Zip](http://www.7-zip.org/)或者[The Unarchiver](https://theunarchiver.com/)。（译者注：国内常用的WinRAR也是支持`.7z`文件解压缩的）

{% capture notice-1 %}

请注意，卡带升级只会更新系统核心组件，如系统设置，桌面菜单，等等。卡带升级不会更新任天堂3DS声音（Nintendo 3DS Sound）和网络相关的组件，如系统迁移，互联网浏览器，StreetPass Mii Plaza，和eShop。

这意味着从一个带有旧版任天堂3DS声音的系统（老3DS欧版、日版、韩版或美版，系统版本在7.0.0以下）卡带升级到一个带有新版任天堂3DS声音的系统会破坏[Soundhax](homebrew-launcher-(soundhax))！你需要一个[替代方法](homebrew-launcher-(mset))进入自制程序启动器！
{% endcapture %}

<div class="notice--warning">{{ notice-1 | markdownify }}</div>

### 你需要

* 最新版本的[Soundhax](http://soundhax.com/) *（针对你的区域，机型和系统版本）*
* 最新版本的[SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest){:target="_blank"}
* 最新版本的[boot9strap](https://github.com/SciresM/boot9strap/releases/latest){:target="_blank"} *（标准版boot9strap；不是`devkit`或`ntr`版）*
* 最新版本的[Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest){:target="_blank"} *(the `.7z` file)*
* 最新版本的[the Homebrew Launcher](https://github.com/fincs/new-hbmenu/releases/latest){:target="_blank"}
* 最新版本的[pre9otherapp](https://github.com/Pirater12/otherapp/releases/latest){:target="_blank"}

### 操作指南

#### 第一部分 - 准备工作

1. 关机
1. 将SD卡插入电脑
1. 将SoundHax的`.m4a`文件复制到SD卡的根目录下
1. 将`otherapp.bin`文件复制到SD卡的根目录下
1. 解压缩Luma3DS`.7z`压缩包，将`boot.firm`文件复制到SD卡的根目录下
1. 将`boot.3dsx`文件复制到SD卡的根目录下
1. 在SD卡根目录创建名为`boot9strap`的文件夹
1. 解压缩boot9strap`.zip`压缩包，将`boot9strap.firm`和`boot9strap.firm.sha`文件复制到SD卡的`/boot9strap/`目录下
1. 解压缩SafeB9SInstaller`.zip`压缩包，复制`arm9.bin`文件到你的SD卡根目录下
1. 将SD卡重新插回机器
1. 开机

#### 第二部分 - 运行SafeB9SInstaller

1. 运行Nintendo 3DS Sound（任天堂3DS声音）

    ![]({{ "/images/screenshots/soundhax-welcome.png" | absolute_url }})
    {: .notice--info}

1. 如果你之前从未打开过Nintendo 3DS Sound，然后出现了一只小鸟提示你如何使用，请过完所有的提示，正常关闭程序，然后重新打开
  + 如果不过完提示就立刻运行SoundHax，会造成每次打开Nintendo 3DS Sound都会有小鸟提示
1. 进入`/SDCARD`目录，播放"<3 nedwill 2016"
  + 可能需要试很多次
  + 如果死机，长按电源键强制关机，然后再试一次

    ![]({{ "/images/screenshots/soundhax-launch.png" | absolute_url }})
    {: .notice--info}

1. 如果漏洞利用成功，你的3DS会进入SafeB9SInstaller

#### 第三部分 - 安装boot9strap

1. 等待所有安全检查完成
1. 按照提示输入按键组合，安装boot9strap
1. 完成后，按(A)键重启机器

#### 第四部分 - 设置Luma3DS

1. 你的机器应该启动到了Luma3DS启动器菜单
  + 如果黑屏，[参见这个问题排查](troubleshooting#black-screen-on-sysnand-boot-after-installing-boot9strap)
1. 通过方向键和(A)键来启用以下设置：
  + **"Show NAND or user string in System Settings"**
1. 按下(Start)键保存设置并重启
  + 如果出现错误，请继续进行接下来的教程

___

### 继续进行[收尾工作](finalizing-setup)
{: .notice--primary}
