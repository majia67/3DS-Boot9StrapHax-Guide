---
title: "GodMode9使用指南"
---

GodMode9是任天堂3DS上一个功能完善的文件浏览器，使你能访问你的SD卡，SysNAND和EmuNAND中的FAT分区，等等。除此之外，你还可以复制，删除，重命名文件，以及创建文件夹。
{: .notice--primary}

请注意，如果在SD卡的`/luma/payloads/`目录下有除了`GodMode9.firm`的其他payload文件，按住(Start)键开机的时候会显示“启动器菜单”，你需要用方向键和(A)键选择"GodMode9"才能继续进行教程中接下来的步骤。
{: .notice--info}

{% capture notice %}
GodMode9威力非常强大。它给你提供了对3DS系统数据进行几乎任何能想得到的修改的途径。不过，它也采取了预防措施，使你不会意外破坏机器上的数据。
<br><br>
写保护系统会发出警告信息，并强制要求你输入按键组合才能解锁写保护。没有输入解锁的按键组合，你就不能覆盖或者修改任何重要的数据，并且你也不可能意外解锁。不过，请还是谨慎一些，并保留备份，以防万一。
{% endcapture %}

<div class="notice--danger">{{ notice | markdownify }}</div>

## <a name="nand_backup" /> 创建NAND备份

#### 操作指南

1. 按住(Start)键开机，运行GodMode9
1. 按(Home)键，打开行动菜单
1. 选择"More..."
1. 选择"Scripts..."
1. 选择"Backup SysNAND"
1. 按(A)键确认
  + 这一步可能需要较长时间
1. 按(A)键继续
1. 按住(R)键的同时按(B)键，弹出SD卡
1. 将SD卡插入电脑
1. 复制`/gm9out`目录下的`nand.bin`和`nand.bin.sha`文件到电脑上的一个安全的位置
  + 如果你之前使用了SafeCTRTransfer，并且创建了名为`<serialnumber>_nand.bin`（serialnumber是你的机器序列号）的系统备份，将其替换为现在的文件（将`nand.bin`重命名为`<serialnumber>_nand.bin`）
  + 在备份文件复制到多个位置（比如网盘）
  + 如果以后系统出现问题，该备份文件可以防止你的机器变砖
1. 复制结束后，删除`/gm9out`目录下的`nand.bin`和`nand.bin.sha`文件
1. 将SD卡插回机器

## <a name="nand_restore" /> 恢复NAND备份

#### 操作指南

1. 按住(Start)键开机，运行GodMode9
1. 进入`[0:] SDCARD`
1. 移动光标到你的NAND `.bin`文件上，按(A)键选中，然后选择"NAND image options..."，然后选择"Restore SysNAND (safe)"
1. 按(A)键解锁SysNAND写保护，然后输入提示的按键组合
  + 这不会覆盖已经安装的boot9strap
1. 输入提示的按键组合，解锁SysNAND (lvl1)写保护
  + 这可能需要一些时间
1. 完成后，按(A)键继续
1. 如果出现提示重新加上写保护，按(B)键取消

## <a name="injectHS" /> 注入任意.CIA应用到Health & Safety（“健康与安全”）应用

#### 准备工作

+ 请将你想要注入的`.cia`文件放到SD卡的`/cias/`目录下
    + 注意你不能注入比“健康与安全”应用更大的文件（包括游戏和其它大型应用）

#### 操作指南

1. 按住(Start)键开机，运行GodMode9
1. 进入`[0:] SDCARD` -> `cias`
1. 选中你想注入的`.cia`文件，按(A)键，并选择"CIA image options..."（CIA镜像选项），然后选择"Mount image to drive"（将镜像挂载到驱动器）
1. 选中`.app`文件，按(A)键，然后选择"NCCH image options"，并选择"Inject to H&S"
1. 按(A)键解锁SysNAND(lvl1)写保护，然后按照提示输入按键组合
1. 按(A)键继续
1. 如果出现提示重新加上写保护，按(A)键确认

## <a name="restore_hs" /> 注入.CIA应用后恢复原始的“健康与安全”应用

本部分教程仅当“健康与安全”应用是通过GodMode9注入的才有效（而非Decrypt9或Hourglass9）。
{: .notice--info}

#### 操作指南

1. 按住(Start)键开机，运行GodMode9
1. 按(Home)键打开行动菜单
1. 选择"More..."
1. 选择"Restore H&S"（恢复健康与安全应用）
1. 按(A)键解锁SysNAND(lvl1)写保护，然后按照提示输入按键组合
1. 如果出现提示重新加上写保护，按(A)键确认

## <a name="dump_cart" /> 导出游戏卡带

#### 准备工作

+ 将想要导出的游戏卡带插入机器
    + 3DS游戏卡带将被导出为可安装的`.cia`格式
    + NDS游戏卡带将被导出为不可安装的`.nds`格式，与烧录卡和模拟器兼容

#### 操作指南

1. 按住(Start)键开机，运行GodMode9
1. 进入`[C:] GAMECART`
1. 选择对应你的游戏卡带的步骤执行：
  + **3DS游戏卡带：**移动光标到`[TitleID].trim.3ds`文件上，按(A)键选中，然后选择"NCSD image options..."，然后选择"Build CIA from file"
  + **NDS游戏卡带：**移动光标到`[TitleID].trim.nds`文件上，按(A)键选中，然后选择"Copy to 0:/gm9/out"
1. 可安装的`.cia`格式文件或不可安装的`.nds`格式文件会被输出到SD卡的`/gm9/out/`目录下

## <a name="dump_title" /> 导出Title

使用FBI内置的`Titles`菜单获取你想要导出的已安装title的Title ID。
{: .notice--info}

#### 操作指南

1. 按住(Start)键开机，运行GodMode9
1. 根据你想要dump的title类型选择对应的分区进入：
  + **用户安装的Title**：进入`[A:] SYSNAND SD`
  + **系统Title**：进入`[1:] SYSNAND CTRNAND`
1. 进入`title`
1. 进入对应Title ID前8位数字的文件夹
1. 进入对应Title ID后8位数字的文件夹
1. 进入`content`
1. 在`.tmd`文件上按(A)键选中，然后选择"TMD file options..."，然后选择"Show title info"
1. 确保你找到了正确的title
1. 按(B)键退出title详情页面
1. 在`.tmd`文件上按(A)键选中，然后选择"TMD file options..."，然后选择"Build CIA (standard)"
1. 可安装的`.cia`格式文件会被输出到SD卡的`/gm9/out/`目录下

## <a name="convert_3ds" /> 将.3DS格式文件转换为.CIA格式文件

#### 准备工作

+ 请将你想要转换的`.3ds`文件放到SD卡的`/cias/`目录下
    + 注意，如果你想要转换烧录卡中的`.3ds`文件，参见[导出游戏卡带](#dump_cart)

#### 操作指南

1. 按住(Start)键开机，运行GodMode9
1. 进入`[0:] SDCARD` -> `cias`
1. 移动光标到`.3ds`文件上，按(A)键选中，然后选择"NCSD image options..."，然后选择"Build CIA from file"
1. 可安装的`.cia`格式文件会被输出到SD卡的`/gm9/out/`目录下

## <a name="backup_gba" /> 备份GBA VC存档

#### 操作指南

1. 关机
1. 取出SD卡，插入电脑中
1. 在`/gm9/`目录下，为每一个你想备份存档的GBA VC游戏创建一个文件夹
1. 将SD卡插回你的机器
1. 开机
1. 为每一个你想备份存档的GBA VC游戏执行如下操作：
  + 运行该GBA VC游戏
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

## <a name="restore_gba" /> 恢复GBA VC存档

#### 操作指南

1. 确保在SD卡的`/gm9/`目录下，每一个你想恢复存档的GBA VC游戏都有一个包含存档备份的文件夹
1. 为每一个你想恢复存档的GBA VC游戏执行如下操作：
  + 运行该GBA VC游戏
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

## <a name="format_sd" /> 格式化SD卡

**注意：这会清除你SD卡上的所有数据！**
{: .notice--danger}

#### 操作指南

1. 按住(Start)键开机，运行GodMode9
1. 按(Home)键，打开行动菜单
1. 选择"More..."
1. 选择"SD format menu"（SD格式化菜单）
1. 按(A)键确认
1. 选择你想要使用的EmuNAND选项
  + 大多数用户会选择"No EmuNAND"
1. 选择"Auto"
1. 按(A)键接受`GM9SD`标签
  + 或者你也可以为SD卡输入一个自定义的名字
1. 按照提示输入按键组合继续

## <a name="crypt_cia" /> 加密/解密.CIA文件

#### 准备工作

+ 请将任何你想加密/解密的`.cia`文件放到SD卡的`/cias/`目录下

#### 操作指南

1. 按住(Start)键开机，运行GodMode9
1. 进入`[0:] SDCARD` -> `cias`
1. 选中你想操作的`.cia`文件，按(A)键，并选择"CIA image options..."（CIA镜像选项）
1. 选择你想使用的功能：
    + **加密并将结果保存到0:/gm9/out:** 为选定的`.cia`文件创建一个加密后的副本，并保存到SD卡的`/gm9/out/`目录下
    + **解密并将结果保存到0:/gm9/out:** 为选定的`.cia`文件创建一个解密后的副本，并保存到SD卡的`/gm9/out/`目录下
    + **加密并替换源文件:** 加密选定的`.cia`文件，并替换源文件
    + **解密并替换源文件:** 解密选定的`.cia`文件，并替换源文件
1. 你加密/解密后的`.cia`文件会被输出到指定的目录下
