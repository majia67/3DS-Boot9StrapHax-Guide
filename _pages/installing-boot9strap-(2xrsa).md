---
title: "安装boot9strap（2xrsa）"
---

### 教程须知
想要解压缩本节教程中的`.7z`压缩包，你需要一个压缩文件管理器，例如[7-Zip](http://www.7-zip.org/)或[The Unarchiver](https://theunarchiver.com/)。（译者注：国内常用的WinRAR也可以）

### 你需要

* 最新版的[SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest){:target="_blank"}
* 最新版的[boot9strap](https://github.com/SciresM/boot9strap/releases/latest){:target="_blank"} *（标准版boot9strap；不是`devkit`或`ntr`版）*
* 最新版的[Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest){:target="_blank"} *（`.7z`压缩包）*
* 最新版的[自制程序启动器](https://github.com/fincs/new-hbmenu/releases/latest){:target="_blank"}

### 操作指南

#### 第一部分 - 准备工作

1. 关机
1. 将SD卡插入电脑
1. 解压Luma3DS`.7z`压缩包，复制`boot.firm`文件到你SD卡的根目录下
1. 复制`boot.3dsx`文件到SD卡根目录
1. 在SD卡根目录创建一个名为`boot9strap`的文件夹
1. 解压缩boot9strap `.zip`压缩包，复制`boot9strap.firm`和`boot9strap.firm.sha`文件到SD卡的`/boot9strap/`目录下
1. 解压缩SafeB9SInstaller `.zip`压缩包，复制`arm9.bin`和`arm11.bin`文件到SD卡根目录

    ![]({{ "/images/screenshots/boot9strap-2xrsa-file-layout.png" | absolute_url }})
    {: .notice--info}

1. 将SD卡插回你的机器
1. 开机

#### 第二部分 - 运行SafeB9SInstaller

1. 打开浏览器，进入以下网址：
  + `http://2xrsa.hacks.guide`
  + 如果你的设备是新3DS、新2DS或老2DS，且没有打开wifi，可以断开充电器并取下电池等几秒钟，即可重新开启wifi
  + 如果出现错误：“当前服务在你的区域不可用”，请使用系统设置修改你的机器所在的国家，匹配你安装的2.1.0 ctr转移镜像所对应的NAND区域
  + 如果在进行CTR转移之前你忘记关闭了家长控制，或者无法访问无线连接设置，请注意你的机器可以自动连接到任何名为`attwifi`的未加密热点
  + 如果出现错误，[参见这个问题排查](troubleshooting#a-browser-based-exploit-is-not-working)
1. 如果漏洞利用成功，机器将运行SafeB9SInstaller

##### 第三部分 - 安装boot9strap

1. 等待所有安全检查完成
1. 按照提示输入按键组合，安装boot9strap
1. 完成后，按(A)键重启机器

##### 第四部分 - 设置Luma3DS

1. 你的机器应该启动到了Luma3DS启动器菜单
  + 如果黑屏，[参见这个问题排查](troubleshooting#black-screen-on-sysnand-boot-after-installing-boot9strap)
1. 通过方向键和A键来启用以下设置：
  + **"Show NAND or user string in System Settings"**
1. 按下(Start)键保存设置并重启
  + 如果出现错误，请继续进行接下来的教程

___

新3DS用户如果系统版本是2.1.0，*必须*在[收尾工作](finalizing-setup)一节之前[恢复NAND备份](godmode9-usage#nand_restore)。
{: .notice--danger}

继续进行[收尾工作](finalizing-setup)
{: .notice--primary}
