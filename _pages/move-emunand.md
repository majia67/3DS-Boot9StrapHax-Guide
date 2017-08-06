---
title: "迁移EmuNAND数据"
---

本节是附加章节，将你的EmuNAND的数据迁移到新的SysNAND自制系统中，然后删除EmuNAND分区。注意EmuNAND和RedNAND是[同一概念](http://3dbrew.org/wiki/NAND_Redirection)的两种略微不同的实现。
{: .notice--info}

请注意，如果在SD卡的`/luma/payloads/`目录下有除了`GodMode9.firm`的其他payload文件，按住(Start)键开机的时候会显示“启动器菜单”，你需要用方向键和(A)键选择"GodMode9"才能继续进行教程中接下来的步骤。
{: .notice--info}

**你必须已经安装了arm9loaderhax + Luma3DS才能执行接下来的操作。**
{: .notice--danger}

#### 你需要

* 已有的EmuNAND
* 最新版本的[GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* 最新版本的[FBI](https://github.com/Steveice10/FBI/releases/latest)

#### 操作指南

##### 第一部分 - 准备工作

1. 关机
1. 取下SD卡，插入电脑中
1. 解压`GodMode9`压缩包，复制`GodMode9.firm`文件（arm9loaderhax用户请使用`GodMode9.bin`文件）到SD卡的`/luma/payloads/`目录下，复制`gm9`文件夹到SD卡根目录下
1. 将SD卡插回你的机器

##### 第二部分 - 备份SysNAND DSiWare存档

如果你没有DSiWare游戏，或者无需备份存档，可以跳过这一节。
{: .notice--info}

1. 按住(Start)键开机，进入GodMode9
1. 如果提示你创建文件备份，按(A)键执行，然后按(A)键继续教程
1. 进入`[2:] SYSNAND TWLN` -> `title`
1. 移动光标到`00030004`目录，按住(R)键的同时按(A)键选中目录，然后选择"Copy to 0:/gm9/out"
  + 如果你有很多DSiWare游戏，这一步可能需要较长时间
1. 按(B)键两次返回主菜单

##### 第三部分 - 备份GBA VC存档

如果你没有GBA VC游戏，或者无需备份存档，可以跳过这一节。
{: .notice--info}

其它类型的模拟器游戏（GBC, NES等）无需备份存档。
{: .notice--info}

1. 按住(R)键的同时按(Start)键关机
1. 取出SD卡，插入电脑中
1. 在`/gm9/`目录下，为每一个你想备份存档的GBA VC游戏创建一个文件夹
1. 将SD卡插回你的机器
1. 开机，进入SysNAND（真实系统）
1. 为每一个你想备份存档的GBA VC游戏执行如下操作：
  + 在SysNAND中运行该GBA VC游戏
  + 退出该GBA VC游戏
  + 关机，按住(Start)键开机，进入Luma3DS启动器菜单
  + 按(A)键运行GodMode9
  + 进入`[S:] SYSNAND VIRTUAL`
  + 选中`gbavc.sav`文件，按(Y)键复制该文件
  + 按(B)键返回主菜单
  + 进入`[0:] SDCARD` -> `gm9`
  + 进入你为该GBA VC游戏创建的文件夹中
  + 按(Y)键粘贴`gbavc.sav`文件
  + 按(Start)键重启机器
1. 关机，按住(Start)键开机，运行GodMode9

##### 第四部分 - 复制EmuNAND到SysNAND

1. 进入`[E:] EMUNAND VIRTUAL`
1. 选中`nand.bin`文件并按(A)键，然后选择"NAND image options..."，然后选择"Restore SysNAND (safe)"
1. 按(A)键解锁SysNAND覆盖保护，然后输入提示的按键组合
  + 这一步不会覆盖你安装的arm9loaderhax
1. 按照提示输入按键组合，解锁(lvl1)写保护
  + 这一步需要较长时间
1. 完成后，按(A)键继续
1. 如果出现提示重新加上写保护，按(B)键取消
1. 按(B)键返回主菜单

##### 第五部分 - 恢复DSiWare存档

如果你之前没有备份DSiWare存档，跳过这一节
{: .notice--info}

1. 进入`[0:] SDCARD` -> `gm9` -> `out`
1. 选中`00030004`目录，按(Y)键复制
1. 按(B)键两次返回主菜单
1. 进入`[2:] SYSNAND TWLN` -> `title`
1. 按(Y)键粘贴`00030004`文件夹
1. 选择"Copy path(s)"（复制路径）
1. 按(A)键解锁SysNAND (lvl1)写保护，然后按照提示输入按键组合
1. 选择"Overwrite file(s)"（覆盖文件）
  + 如果你有很多DSiWare游戏，这一步可能需要较长时间
1. 如果出现提示重新加上写保护，按(B)键取消
1. 按(B)键两次返回主菜单

##### 第六部分 - 恢复GBA VC存档

如果你之前没有备份GBA VC存档，跳过这一节
{: .notice--info}

1. 按住(R)键的同时按(Start)键关机
1. 开机，进入SysNAND（真实系统）
1. 为每一个你想恢复存档的GBA VC游戏执行如下操作：
  + 在SysNAND中运行该GBA VC游戏
  + 退出该GBA VC游戏
  + 关机，按住(Start)键开机，进入Luma3DS启动器菜单
  + 按(A)键运行GodMode9
  + 进入`[0:] SDCARD` -> `gm9`
  + 进入你为该GBA VC游戏创建的文件夹中
  + 选中`gbavc.sav`文件，按(Y)键复制该文件
  + 按(B)键返回主菜单
  + 进入`[S:] SYSNAND VIRTUAL`
  + 按(Y)键粘贴`gbavc.sav`文件
  + 按(A)键确认
  + 按(Start)键重启机器
1. 按住(Start)键重启，运行GodMode9

##### 第七部分 - 备份SysNAND

1. 按(Home)键，打开行动菜单
1. 选择"More..."
1. 选择"Scripts..."
1. 选择"Backup SysNAND"
1. 按(A)键确认
  + 这一步可能需要较长时间
1. 按(A)键继续
1. 按住(R)键的同时按(B)键，弹出SD卡
1. 将SD卡插入电脑
1. 复制`/gm9out`目录下的`<serialnumber>_nandmin_###.bin`文件（serialnumber是你的机器序列号）到电脑上的一个安全的位置
  + 在备份文件复制到多个位置（比如网盘）
  + 如果以后系统出现问题，该备份文件可以防止你的机器变砖
1. 复制结束后，删除`/gm9/out`目录下的`<serialnumber>_nandmin_###.bin`文件
1. **在你的电脑上创建一个文件夹，将SD卡上的所有文件复制到里面。在接下来的步骤中SD卡上的所有文件将被删除**

##### 第八部分 - 格式化SD卡

1. 将SD卡插回你的机器
1. 按(Home)键，打开行动菜单
1. 选择"More..."
1. 选择"SD format menu"（SD格式化菜单）
1. 按(A)键确认
1. 选择"No EmuNAND"
1. 选择"Auto"
1. 按(A)键接受`GM9SD`标签
  + 或者你也可以为SD卡输入一个自定义的名字
1. 按照提示输入按键组合继续
1. 格式化完成后，按住(R)键的同时按(B)键，弹出你的SD卡
1. 将SD卡插入电脑
1. 将之前备份的文件复制回SD卡
  + 确保你使用备份的`boot.firm`文件替换了SD卡上已有的文件
1. 将SD卡插回你的机器
1. 按(A)键重新加载你的SD卡
1. 按(Start)键保存并重启
1. 如果出现黑屏，[参见这个问题排查](troubleshooting#ts_sys_down)

---

返回到[收尾工作](finalizing-setup)继续操作。
{: .notice--primary}
