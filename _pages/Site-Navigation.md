---
title: "网站导航"
layout: single-no-ads
sitemap: false
permalink: /site-navigation.html
lang: zh_CN
ref: site-navigation
---

{% capture notice-1 %}
**常用链接**

+ [安装arm9loaderhax](installing-arm9loaderhax)
+ [自制程序启动器（声音破解）](homebrew-launcher-(soundhax))
+ [SafeCTRTransfer（自制程序启动器）](safectrtransfer-(homebrew-launcher))
{% endcapture %}
<div class="notice--info">{{ notice-1 | markdownify }}</div>

{% capture notice-2 %}
**全部链接**

{% assign site_pages = site.pages | sort:"title" %}
{% for node in site_pages %}
{% if node.path contains "zh_CN" %}
+ <a href="{{node.url}}">{{node.title}}</a>
{% endif %}
{% endfor %}

{% endcapture %}
<div class="notice--primary">{{ notice-2 | markdownify }}</div>
