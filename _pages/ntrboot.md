---
title: "ntrboot"
---

如果你已经将ntrboot刷入你的烧录卡带中，或者你的烧录卡已经自带了ntrboot，你可以跳过这一步，直接进入[安装boot9strap（ntrboot）](installing-boot9strap-(ntrboot))进行操作。

{: .notice--success}

### 教程须知

使用ntrboot安装boot9strap需要将ntrboot刷入兼容的NDS / DSi烧录卡带。有些烧录卡带已经预先刷入了ntrboot。

尽管ntrboot破解不依赖系统版本，ntrboot刷入器（将ntrboot刷入卡带的软件）却依赖某些特定系统版本。这意味着，取决于你的机器区域和系统版本，只有某些方法适合你。

请注意，带有“时间炸弹”字样的卡带在检测到系统日期晚于某个卡带固件设定的日期之后，将无法运行`.nds`文件。跳过这个限制的方法之一是将系统时间设置到一个更早的日期。

| 卡带名 | 当前价格 | “时间炸弹”？ | 3DS版本？ | DSi版本？ | 备注 |
|-|-:|:-:|:-:|:-:|-|
| [**R4i-SDHC B9S**](http://www.nds-card.com/ProShow.asp?ProID=574) | $15.99 | 2019.9.3 | <= 11.6.0 | <= 1.4.5 | **自带ntrboot**；可以被重新刷回成普通的NDS烧录卡 |
| [**R4i Gold 3DS Plus**](http://www.nds-card.com/ProShow.asp?ProID=575) | $19.99 | 无 | <= 11.6.0 | <= 1.4.5 | **自带ntrboot** ([内置ntrboot和NDS模式的切换]({{ "/images/screenshots/r4i-gold-3ds-plus.png" | absolute_url }}))；不要自行刷入ntrboot。 |
| [**Acekard 2i**](http://www.nds-card.com/ProShow.asp?ProID=160) | $20.99 | 无 | <= 4.3.0 | <= 1.4.4 | |
| [**DSTT**](http://www.nds-card.com/ProShow.asp?ProID=157) | $9.99 | 无 | 不适用 | 不适用 | 仅带有[部分闪存芯片](https://gist.github.com/Hikari-chin/6b48f1bb8dd15136403c15c39fafdb42)的版本支持ntrboot。 |
| [**R4i Gold 3DS**](http://www.nds-card.com/ProShow.asp?ProID=149) | $19.99 | 无 | <= 11.6.0 | <= 1.4.5 | 所有RTS版本均兼容。 |
| [**R4i-SDHC 3DS RTS**](http://www.nds-card.com/ProShow.asp?ProID=146) | $13.99 | 1.87: 2019.9.3 | <= 11.6.0 | <= 1.4.5 | |
| [**R4iSDHC GOLD Pro 20XX**](http://www.nds-card.com/ProShow.asp?ProID=490) | $9.99 | 3.9b: 2019.9.3 | <= 11.6.0 | <= 1.4.5 | 所有R4iSDHC 20XX烧录卡都是相同的。2013款不兼容。 |
| [**R4iSDHC RTS LITE 20XX**](http://www.nds-card.com/ProShow.asp?ProID=450) | $13.99 | 3.9b: 2019.9.3 | <= 11.6.0 | <= 1.4.5 | 所有R4iSDHC 20XX烧录卡都是相同的。2013款不兼容。 |
| **Ace3DS X** | | 无 | <= 11.6.0 | <= 1.4.5 | **自带ntrboot**（外置ntrboot ("3DS")和NDS模式的切换）；不要自行刷入ntrboot。|
| **Ace3DS Plus** | | 无 | <= 11.6.0 | <= 1.4.5 | |
| **Gateway Blue** | | 无 | 4.1.0 - 4.5.0 | <= 1.4.5 | |
| **Infinity 3 R4i** | | 无 | <= 11.6.0 | <= 1.4.5 | |
| **R4 3D Revolution** | | 无 | 不适用 | 不适用 | |
| **R4i Gold 3DS Deluxe "Starter"** | | 无 | 4.1.0 - 4.5.0 | <= 1.4.5 | |
| **R4i Ultra** | | 无 | <= 4.3.0 | <= 1.4.5 | |
| **R4i-SDHC 3DS RTS Deluxe Edition** | | 未知 | <= 11.6.0 | <= 1.4.5 | |
| **R4iSDHC Dual-Core 20XX** | | 3.9b: 2019.9.3 | <= 11.6.0 | <= 1.4.5 | 所有R4iSDHC 20XX烧录卡都是相同的。 |

  ![]({{ "/images/screenshots/ntrboot-flashcarts.png" | absolute_url }})
  {: .notice--info}

在开始教程前，确保你的烧录卡在你的机器上可以运行`.nds`文件。某些烧录卡需要将固件或“内核”文件拷贝到烧录卡的SD卡中，具体方法请参照你的烧录卡的说明。

请注意某些方法可能有额外的兼容性要求。

如果你的机器是合盖的版本（所有3DS和新2DS），那么不管刷入方法是什么，使用这个漏洞都需要有一个小磁铁。这是因为漏洞需要你的机器在能触碰按键的情况下进入睡眠模式。

如果要测试磁铁能不能工作，将机器开机，然后用磁铁靠近(A)(B)(X)(Y)键，看能不能进入睡眠模式。如果能进入，在磁铁靠近的情况下上下屏幕都会变黑。
{: .notice--info}

烧录卡在安装了ntrboot漏洞之后将不能使用其正常功能（除了Acekard 2i *仅能在NDS和自制3DS系统上使用*）。这意味着大多数烧录卡甚至不会在桌面上显示。在ntrboot刷入操作结束后，你可以选择将它从烧录卡中删除。

在某些罕见的情况下，刷入操作可能会造成盗版烧录卡**变砖**，使其永远无法使用。仅原装的在表中列出的烧录卡支持ntrboot。为减少买到盗版烧录卡的几率，推荐你在一个有信誉的网站上购买烧录卡（例如[NDS Card](http://www.nds-card.com/)）。（译者注：国内渠道较多，淘宝上建议选销量较大的商家，或者烧录卡官网链接的网店）。
{: .notice--danger}

___
### 刷入方法

___

#### 刷入ntrboot（3DS单系统）

本方法仅需你的未破解的3DS和一个兼容的烧录卡。本方法通过烧录卡运行一个刷入ntrboot的`.nds`文件。这意味着你的烧录卡必须支持在你的3DS上运行`.nds`文件。参见上面的烧录卡列表了解更多信息。

进入[刷入ntrboot（3DS单系统）](flashing-ntrboot-(3ds-single-system))
{: .notice--primary}

___

#### 刷入ntrboot（3DS多系统）

本方法需要用到另一个已经运行boot9strap的3DS家族机器。这对你的烧录卡支持的系统版本没有任何要求。参见上面的烧录卡列表了解更多信息。

进入[刷入ntrboot（3DS多系统）](flashing-ntrboot-(3ds-multi-system))
{: .notice--primary}

___

#### 刷入ntrboot (NDS)

本方法需要用到另一个与你的烧录卡兼容的Nintendo DS或Nintendo DS Lite机器。本方法需要你的烧录卡能在你的NDS上运行ntrboot刷入器`.nds`文件。

进入[刷入ntrboot（NDS）](flashing-ntrboot-(nds))
{: .notice--primary}

___

#### 刷入ntrboot (DSi)

本方法需要用到另一个与你的烧录卡兼容的Nintendo DSi机器。本方法需要你的烧录卡能在你的DSi上运行ntrboot刷入器`.nds`文件。

进入[刷入ntrboot（DSi）](flashing-ntrboot-(dsi))
{: .notice--primary}
