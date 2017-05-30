---
title: "开始教程"
---

本节教程将指导你在*未破解*的3DS或2DS上安装boot9strap。如果你已经安装了arm9loaderhax，并想升级到boot9strap，参见[升级到boot9strap](updating-to-boot9strap)。
{: .notice--primary}

图片中机器的颜色可能会不同，但是请特别关注按键的布局和每台机器的特点，确保你选择了正确的机型。
{: .notice}

请点击对应你机器的图片进入对应的教程页面。
{: .notice--primary}

不同的机型、版本和区域需要不同的步骤以实现boot9strap自制固件。下面的一系列页面将会帮助你针对你的设备找到适合的开始方案。
{: .notice--info}

如果你已经破解过你的3DS，并安装了基于EmuNAND的自制系统，请仍然依照SysNAND的版本进行操作。你的数据将会从EmuNAND转移到B9S破解系统上面。
{: .notice--info}

注意本教程中的屏幕截图可以点击放大以显示更多的细节。
{: .notice--info}

Windows系统用户在开始之前需要开启[显示文件扩展名](file-extensions-(windows))的选项！
{: .notice--info}

开始之前，你可能想检测一下SD卡错误。可以使用[H2testw (Windows)](h2testw-(windows))，[F3 (Linux)](f3-(linux))，[F3X (Mac)](f3x-(mac))。
{: .notice--warning}

注意，新的[安装boot9strap（硬改）](installing-boot9strap-(hardmod))方法适用于*任何设备、区域和系统版本*！这包括之前无法破解的神游和台版机！
{: .notice--success}

{% capture notice-1 %}
我们收到一系列有关使用自制系统被任天堂封号的报告。为了保护你自己，请在开始本破解教程之前执行如下步骤：

1. 依次进入系统设置 -> "Internet Settings" （互联网设置） -> "SpotPass" -> "Sending of System Information"（发送系统信息）
1. 禁用"Sending of System Information"（发送系统信息）选项
1. 退出系统设置
1. 进入你的朋友列表（Home菜单上面一排图标中的笑脸图标）
  + 如果出现错误并退出了菜单，那么朋友列表设置已经被禁用了
1. 进入朋友列表设置 -> "Friend Notification Settings"（朋友通知设置） ->  "Show friends what you're playing"（告诉朋友们你在玩什么）
1. 禁用"Show friends what you're playing"（告诉朋友们你在玩什么）选项
1. 退出朋友列表

{% endcapture %}

<div class="notice--danger">{{ notice-1 | markdownify }}</div>

| 新3DS | 老3DS 或 2DS |
|:-:|:-:|
| [![新3DS](images/new3ds.png)](get-started-(new-3ds)) <br><br> [![新3DS XL](images/new3dsxl.png)](get-started-(new-3ds)) | [![老3DS](images/old3ds.png)](get-started-(old-3ds)) &nbsp;&nbsp; [![老3DS XL](images/old3dsxl.png)](get-started-(old-3ds)) <br><br> [![2DS](images/2ds.png)](get-started-(old-3ds)) |
