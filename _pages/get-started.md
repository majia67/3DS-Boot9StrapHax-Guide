---
title: "开始教程"
---

### 教程须知

不同的机型和系统版本安装boot9strap自制固件的的步骤并不一样。本页面将会帮助你找到合适的方案。

请点击对应你机器的图片进入相应的教程页面。图片中机器的颜色可能会不同，但是请特别关注按键的布局和每台机器的特点，确保你选择了正确的机型。

如果你已经破解过你的3DS，并安装了基于EmuNAND的自制系统，请仍然依照SysNAND的版本进行操作。你的数据将会从EmuNAND转移到B9S破解系统上面。如果你使用了menuhax，你需要在开始教程之前[清空主菜单的extdata](troubleshooting#clear-home-menu-extdata)。

本节教程将指导你在*未破解*的3DS或2DS上安装boot9strap。如果你已经安装了arm9loaderhax，并想升级到boot9strap，参见[从A9LH升级到B9S](a9lh-to-b9s)。
{: .notice--primary}

Windows系统用户在开始之前需要开启[显示文件扩展名](file-extensions-(windows))的选项！
{: .notice--info}

开始之前，你可能想检测一下SD卡错误。可以使用[H2testw (Windows)](h2testw-(windows))，[F3 (Linux)](f3-(linux))，[F3X (Mac)](f3x-(mac))。
{: .notice--warning}

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

### 设备列表

<table>
  <colgroup>
    <col span="1" style="width: 50%;">
    <col span="1" style="width: 50%;">
  </colgroup>
  <thead>
    <tr>
      <th style="text-align: center">新3DS或新2DS</th>
      <th style="text-align: center">老3DS或老2DS</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center"><a href="get-started-(new-3ds)"><img src="{{ base_path }}/images/new3ds.png" style="padding: 0.5em;"></a> <a href="get-started-(new-3ds)"><img src="{{ base_path }}/images/new3dsxl.png" style="padding: 0.5em;"></a> <a href="get-started-(new-3ds)"><img src="{{ base_path }}/images/new2dsxl.png" style="padding: 0.5em;"></a></td>
      <td style="text-align: center"><a href="get-started-(old-3ds)"><img src="{{ base_path }}/images/old3ds.png" style="padding: 0.5em;"></a> <a href="get-started-(old-3ds)"><img src="{{ base_path }}/images/old3dsxl.png" style="padding: 0.5em;"></a> <a href="get-started-(old-3ds)"><img src="{{ base_path }}/images/2ds.png" style="padding: 0.5em;"></a></td>
    </tr>
  </tbody>
</table>
