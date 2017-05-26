---
title: "卡带升级"
permalink: /cart-update.html
lang: zh_CN
ref: cart-update
---

所有的游戏卡带都自带一份所需版本系统的拷贝，使得低版本系统的玩家即使在没有互联网链接的情况下，也可以用卡带升级到所需的系统版本
{: .notice--info}

{% capture notice-1 %}
卡带升级只会更新系统核心组件，如系统设置，桌面菜单，等等。卡带升级不会更新任天堂3DS声音（Nintendo 3DS Sound）和网络相关的组件，如系统迁移，互联网浏览器，StreetPass Mii Plaza，和eShop。
<br><br>
这意味着从一个带有旧版任天堂3DS声音的系统（老3DS欧版、日版、韩版或美版，系统版本在7.0.0以下）卡带升级到一个带有新版任天堂3DS声音的系统会破坏[Soundhax](homebrew-launcher-(soundhax))！你需要一个[替代方法](homebrew-launcher-(alternatives))进入自制程序启动器！
{% endcapture %}

<div class="notice--warning">{{ notice-1 | markdownify }}</div>

这也意味着卡带升级不会在你没有浏览器的情况下给你安装一个浏览器。它**只会**升级实际的系统版本*（例如，2.1.0-0 -> 6.0.0-0）*。版本号的最后一位*（即-0）* **不会**变更。
{: .notice--warning}

**使用带有9.9.0及以上系统版本的游戏卡带进行升级会删除你的浏览器，联网升级系统之后才会恢复！**
{: .notice--danger}

#### 你需要

* 一张游戏卡带，内含你想要升级到的[系统版本](http://www.3dsdb.com/)

#### 操作指南

1. 开机时同时按住(L) + (R) + (A) + (UP)键，进入恢复模式
1. 如果出现提示，取消升级
1. 重启
1. 插入游戏卡带
1. 尝试运行游戏
1. 出现提示后，选择更新
