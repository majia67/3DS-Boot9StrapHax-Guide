---
title: "网站导航"
layout: single-no-ads
sitemap: false
---

{% capture notice-1 %}
**常用链接**

+ [升级至boot9strap](updating-to-boot9strap)
+ [自制程序启动器（声音破解）](homebrew-launcher-(soundhax))
+ [安装Boot9Strap（自制程序启动器）](installing-boot9strap-(homebrew-launcher))
+ [收尾工作](finalizing-setup)
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
