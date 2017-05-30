---
title: "安装Boot9Strap（DSiWare）"
---

在11.4.0的系统版本上有两种使用DSiWare安装boot9strap的方法。
{: .notice--info}

其中一个方法仅能在四种特定的游戏上有效，且这四种游戏都不再在eShop上销售；另一种方法还能在不少游戏上有效，且这些游戏还在eShop上有售。
{: .notice--info}

这两种方法都需要两台机器。其中一台机器必须已经运行某种自制系统（boot9strap或arm9loaderhax），我们称为*来源3DS*；另一台机器系统版本在11.4.0，我们称为*目标3DS*。
{: .notice--info}

两台3DS必须属于同一区域。
{: .notice--warning}

这两种方法都假设*来源3DS*是按照本教程安装了boot9strap，或按照原来的教程安装了arm9loaderhax。虽然用其它的自制系统也能达到目的，但这超出了本教程的范围。
{: .notice--info}

这两种方法都使用了一系列"FIRM partitions known-plaintext"漏洞（参见[这里](https://www.3dbrew.org/wiki/3DS_System_Flaws)），而且还利用了一个3DS/2DS系统设计上的缺陷，使得DSiWare titles能在已加密的NAND的任意位置进行读写。
{: .notice--info}

{% capture notice-4 %}
这两种方法都需要你从已破解的3DS[系统迁移](http://en-americas-support.nintendo.com/app/answers/detail/a_id/13996/)至未破解的3DS。系统迁移*仅*支持如下方向的迁移：
  + 新3DS -> 新3DS
  + 老3DS或2DS -> 老3DS或2DS
  + 老3DS或2DS -> 新3DS
{% endcapture %}

<div class="notice--warning">{{ notice-4 | markdownify }}</div>

来源3DS的NNID会被迁移到目标3DS上，除非你再迁移回来，或者联系任天堂（教程中会有具体细节）！
{: .notice--danger}

系统迁移每周只能进行一次。
{: .notice--danger}

{% capture notice-1 %}

[安装boot9strap（DSiWare存档注入）](installing-boot9strap-(dsiware-save-injection))
<br><br>
本方法需要来源3DS上已经安装了正版的下列游戏中的任一个：

    + **Fieldrunners**
    + **Legends of Exidia**
    + **Guitar Rock Tour**
    + **The Legend of Zelda: Four Swords**

盗版*不能*用来破解，并且这些游戏都已经从eShop下架。

{% endcapture %}

<div class="notice--primary">{{ notice-1 | markdownify }}</div>

{% capture notice-1 %}

[安装boot9strap（DSiWare游戏注入）](installing-boot9strap-(dsiware-game-injection))
<br><br>
本方法需要来源3DS上购买或者已经安装了正版的[安装boot9strap（DSiWare可注入游戏列表）](installing-boot9strap-(dsiware-game-injection-list)) 页面中的任一个游戏。
<br><br>
盗版*不能*用来破解。

{% endcapture %}

<div class="notice--primary">{{ notice-1 | markdownify }}</div>