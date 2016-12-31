---
title: "Decrypt9（自制程序启动器）"
permalink: /decrypt9-(homebrew-launcher).html
---

如果你的3DS之前已经破解，并安装了基于EmuNAND的自制系统，请务必注意本教程仅适用于SysNAND，教程内的步骤应当应用在你的SysNAND上。注意EmuNAND和RedNAND是[同一概念](http://3dbrew.org/wiki/NAND_Redirection)的两种略微不同的实现。
{: .notice--info}

#### 你需要

* 最新版本的[Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/)

#### 操作指南

1. 在SD卡根目录下创建`files9`文件夹（如果没有的话）
3. 复制Decrypt9WIP压缩包中的`Decrypt9WIP`文件夹到你SD卡的`/3ds/`目录下
3. 将SD卡重新插入你的3DS
4. 进入自制程序启动器
4. 打开Decrypt9WIP **（有可能需要尝试多次）**
    + 如果你尝试了很多次以后，还是不能进入Decrypt9WIP，你很有可能是处在“部分降级”的阶段。请参考[降级到9.2.0](9.2.0-downgrade)页面
4. 进入"SysNAND Options"，选"SysNAND Backup/Restore"
5. 选择"NAND Backup (min size)"，将你的NAND备份到`NANDmin.bin`文件中
6. 返回到主菜单

继续进行[2.1.0 ctr迁移](2.1.0-ctrtransfer)    
{: .notice--primary}
