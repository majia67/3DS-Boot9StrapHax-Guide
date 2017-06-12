---
title: "开始教程（老3DS）"
---

请在下表中按照你的系统版本选择对应的页面。
{: .notice--primary}

{% capture notice-1 %}
下面表格的最后两列对应着你系统版本的结尾数字（代表着安装在系统中浏览器的版本）。如果版本号以0结尾，则说明没有浏览器，如果大于0则表示浏览器已经安装。
<br><br>
“从”和“到”两列分别包含各自对应的版本号。也就是说，举个例子“从9.0.0到9.2.0”这一行表示9.0.0，9.1.0，和9.2.0。
<br><br>
例如，如果系统版本为“5.0.0-0U”，你需要定位到“无浏览器”这一列和“从5.0.0到5.1.0”这一行，因为系统版本在那个范围内并且无浏览器 。
{% endcapture %}

<div class="notice--info">{{ notice-1 | markdownify }}</div>

所有版本的机器都可以通过[卡带升级](cart-update)，将系统升级到更高版本，然后按照升级后的系统版本选择教程。
{: .notice--warning}

{% capture notice-1 %}
卡带升级只会更新系统核心组件，如系统设置，桌面菜单，等等。卡带升级不会更新任天堂3DS声音（Nintendo 3DS Sound）和网络相关的组件，如系统迁移，互联网浏览器，StreetPass Mii Plaza，和eShop。
<br><br>
这意味着从一个带有旧版任天堂3DS声音的系统（老3DS欧版、日版、韩版或美版，系统版本在7.0.0以下）卡带升级到一个带有新版任天堂3DS声音的系统会破坏[Soundhax](homebrew-launcher-(soundhax))！你需要一个[替代方法](homebrew-launcher-(alternatives))进入自制程序启动器！
{% endcapture %}

<div class="notice--warning">{{ notice-1 | markdownify }}</div>

如果你是从包含9.9.0或以上的游戏卡带升级而来*(这说明你的系统已经是9.9.0或以上版本，但你的浏览器还是以-25或更低结尾，比方说10.2.0-24)*, 你的浏览器已经被删除了，请看“无浏览器”列。
{: .notice--warning}

系统版本号可以在系统设置中上屏幕的右下方找到。
{: .notice--success}

![]({{ base_path }}/images/screenshots/system-version.png)
{: .notice--info}

<table>
  <colgroup>
    <col span="1" style="width: 10%;">
    <col span="1" style="width: 10%;">
    <col span="1" style="width: 40%;">
  </colgroup>
  <thead>
    <tr>
      <th style="text-align: center">从</th>
      <th style="text-align: center">到</th>
      <th style="text-align: center">无浏览器</th>
      <th style="text-align: center">有浏览器</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center">1.0.0</td>
      <td style="text-align: center">1.1.0</td>
      <td style="text-align: center" colspan="2"><a href="installing-boot9strap-(hardmod)">安装boot9strap（硬改）</a></td>
    </tr>
    <tr>
      <td style="text-align: center">2.1.0</td>
      <td style="text-align: center">2.1.0</td>
      <td style="text-align: center"><a href="installing-boot9strap-(hardmod)">安装boot9strap（硬改）</a></td>
      <td style="text-align: center"><a href="installing-boot9strap-(2xrsa)">安装boot9strap（2xrsa）</a></td>
    </tr>
    <tr>
      <td style="text-align: center">2.2.0</td>
      <td style="text-align: center">3.1.0</td>
      <td style="text-align: center" colspan="2"><a href="installing-boot9strap-(hardmod)">安装boot9strap（硬改）</a></td>
    </tr>
    <tr>
      <td style="text-align: center">4.0.0</td>
      <td style="text-align: center">4.5.0</td>
      <td style="text-align: center"><a href="installing-boot9strap-(mset)">安装boot9strap（系统设置）</a></td>
      <td style="text-align: center"><a href="installing-boot9strap-(browser)">安装boot9strap（浏览器）</a></td>
    </tr>
    <tr>
      <td style="text-align: center">5.0.0</td>
      <td style="text-align: center">5.1.0</td>
      <td style="text-align: center"><a href="installing-boot9strap-(hardmod)">安装boot9strap（硬改）</a></td>
      <td style="text-align: center"><a href="installing-boot9strap-(browser)">安装boot9strap（浏览器）</a></td>
    </tr>
    <tr>
      <td style="text-align: center">6.0.0</td>
      <td style="text-align: center">6.3.0</td>
      <td style="text-align: center"><a href="installing-boot9strap-(mset)">安装boot9strap（系统设置）</a></td>
      <td style="text-align: center"><a href="installing-boot9strap-(browser)">安装boot9strap（浏览器）</a></td>
    </tr>
    <tr>
      <td style="text-align: center">7.0.0</td>
      <td style="text-align: center">8.1.0</td>
      <td style="text-align: center"><a href="installing-boot9strap-(hardmod)">安装boot9strap（硬改）</a></td>
      <td style="text-align: center"><a href="installing-boot9strap-(browser)">安装boot9strap（浏览器）</a></td>
    </tr>
    <tr>
      <td style="text-align: center">9.0.0</td>
      <td style="text-align: center">11.3.0</td>
      <td style="text-align: center" colspan="2"><a href="homebrew-launcher-(soundhax)">自制程序启动器（声音破解）</a></td>
    </tr>
    <tr>
      <td style="text-align: center">11.4.0</td>
      <td style="text-align: center">11.4.0</td>
      <td style="text-align: center" colspan="2"><a href="installing-boot9strap-(dsiware)">安装boot9strap（DSiWare）</a></td>
    </tr>
    <tr>
      <td style="text-align: center; font-weight: bold;" colspan="2">任何系统版本<br></td>
      <td style="text-align: center; font-weight: bold;" colspan="2"><p style="display: inline-block; margin-top: 1.3em; width: 47%"><a href="installing-boot9strap-(ntrboothax)">安装boot9strap（ntrboothax）</a><br><sub>（需要兼容的烧录卡带）</sub></p><p style="display: inline-block; margin-top: 1.3em; vertical-align: super; width: 6%">或</p><p style="display: inline-block; margin-top: 1.3em; width: 47%"><a href="installing-boot9strap-(hardmod)">安装boot9strap（硬改）</a><br><sub>（需要拆机）</sub></p></td>
    </tr>
  </tbody>
</table>

