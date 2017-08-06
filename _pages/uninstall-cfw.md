---
title: "删除自制系统"
---

本节教程将指导你完全删除机器上的自制系统，包括Boot9Strap和Luma3DS，将你的机器恢复成原生系统状态。
{: .notice--danger}

任何未签名的（盗版的）游戏会显示为不可用，可以自行从"System Settings"（系统设置）中的"Data Management"（数据管理）一节删去。请使用[存档管理器](https://github.com/J-D-K/JKSM/releases/latest)备份你想保留的盗版游戏存档。
{: .notice--info}

这不会影响你的NNID，任何已购买的正版游戏，以及它们的存档。
{: .notice--info}

请注意，如果在SD卡的`/luma/payloads/`目录下有除了`GodMode9.firm`的其他payload文件，按住(Start)键开机的时候会显示“启动器菜单”，你需要用方向键和(A)键选择"GodMode9"才能继续进行教程中接下来的步骤。
{: .notice--info}

#### 你需要

* 最新版本的[GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* 对应你的机器版本的卸载脚本:
  + 新3DS / 新2DS：[`uninstall_hax_retail_NEW.gm9`]({{ base_path }}/gm9_scripts/uninstall_hax_retail_NEW.gm9)
  + 老3DS / 老2DS[`uninstall_hax_retail_OLD.gm9`]({{ base_path }}/gm9_scripts/uninstall_hax_retail_OLD.gm9)

#### 操作指南

##### 第一部分 - 准备工作

1. 关机
1. 将SD卡插入电脑
1. 解压GodMode9`.zip`压缩包，复制`GodMode9.firm`到SD卡的`/luma/payloads/`目录下，复制`gm9`文件夹到SD卡根目录下
1. 复制对应你的机器版本的卸载脚本到SD卡的`/gm9/scripts/`目录下
1. 将SD卡插回机器
1. 开机

##### 第二部分 - 运行卸载脚本

1. 按住(Start)键开机，运行GodMode9
1. 如果提示你创建文件备份，按(A)键执行，然后按(A)键继续教程
1. 按(Home)键打开行动菜单
1. 选择"More..."（更多）
1. 选择"Scripts..."（脚本）
1. 选择卸载脚本
1. 出现提示时，按(A)键继续
1. 按(A)键解锁SysNAND(lvl3)写保护，然后按照提示输入按键组合
1. 按(A)键继续
1. 按(A)键重新加上写保护
1. 按(Start)键重启

___

所有自制系统已经从你的机器上删除了
{: .notice--success}

你可以删除SD卡上任何**除了**`Nintendo 3DS`或`DCIM`之外的文件和文件夹。
{: .notice--info}