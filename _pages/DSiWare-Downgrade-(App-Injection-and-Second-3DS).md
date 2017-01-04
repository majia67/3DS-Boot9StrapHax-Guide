---
title: "DSiWare降级（App注入和第二台3DS）"
permalink: /dsiware-downgrade-(app-injection-and-second-3ds).html
---

如果你的系统版本在11.0.0至11.2.0，你可以参照本节教程，使用DSiWare和第二台已经装有自制固件的3DS降级你的NATIVE_FIRM。第二台3DS用来导出和恢复你的系统固件（NAND）。
{: .notice}

如果你的两台3DS中有系统版本低于11.2.0的，你需要在每台系统版本低于11.2.0的3DS上执行ctr-httpwn步骤（当提示时），使你能在它们上面进行系统迁移。
{: .notice--info}

本方法利用了一个设计上的缺陷，能让DSiWare titles在固件的任何地方读写。
{: .notice--info}

本方法是"FIRM partitions known-plaintext"漏洞的一种目前有效的实现。详情参见[这里](https://www.3dbrew.org/wiki/3DS_System_Flaws)。
{: .notice--info}
{: .notice--info}

本节教程假定运行自制固件的3DS运行的是arm9loaderhax，并且是通过本教程安装的。不过做一些小的修改后（例如在EmuNAND上执行教程中所有针对SysNAND的操作）也适用于运行EmuNAND的系统。注意EmuNAND和RedNAND是[同一概念](http://3dbrew.org/wiki/NAND_Redirection)的两种略微不同的实现。
{: .notice--info}

你的DSiWare的存档在被替换为破解存档前会进行备份。
{: .notice--info}

{% capture notice-4 %}
本破解教程需要你从已破解的3DS[系统迁移](http://en-americas-support.nintendo.com/app/answers/detail/a_id/13996/)至未破解的3DS。系统迁移*仅*支持如下方向的迁移：    
  + 新3DS -> 新3DS    
  + 老3DS或2DS -> 老3DS或2DS    
  + 老3DS或2DS -> 新3DS    
{% endcapture %}

<div class="notice--warning">{{ notice-4 | markdownify }}</div>

两台3DS必须属于同一区域。
{: .notice--warning}

**_目标3DS_上的所有数据都将被清除！**
{: .notice--danger}

来源3DS的NNID会被迁移到目标3DS上，除非你再迁移回来，或者联系任天堂（教程中会有具体细节）！
{: .notice--danger}

系统迁移每周只能进行一次。
{: .notice--danger}

#### 你需要

* 两台3DS系统
  + **来源3DS**：运行*最新系统版本*自制固件（arm9loaderhax或某种EmuNAND/RedNAND）的3DS
  + **目标3DS**：运行原生系统的3DS（版本在*11.0.0至11.2.0*）
* **来源3DS**上已经购买（或原来就有）并安装了一个eShop版的DSiWare游戏
  + 使用盗版游戏**无效**
  + 参见[DSiWare列表](dsiware-list)页面查看合适的游戏
* 自制程序启动器进入点，参见[自制程序启动器（声音破解）](homebrew-launcher-(soundhax))或[自制程序启动器（无浏览器）](homebrew-launcher-(no-browser))
* 对应你3DS所在区域的sudokuhax注入包
  + [（美版）`DSiWare_usa_sudokuhax_injection.zip`](magnet:?xt=urn:btih:7ed7fee15c900ed02b5e2cb3c8e7a0363f4d9354&dn=DSiWare_usa_sudokuhax_injection.zip&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce)
  + [（欧版）`DSiWare_eur_exidiahax_injection.zip`](magnet:?xt=urn:btih:046bb8023bc40b9a95a8a339c85a9ef18cf60db6&dn=DSiWare_eur_exidiahax_injection.zip&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce)
  + [（日版）`DSiWare_jpn_4swordshax_injection.zip`](magnet:?xt=urn:btih:1bcc90c93da91c9876671f6218084207def90db9&dn=DSiWare_jpn_4swordshax_injection.zip&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce)
* 最新版的[GodMode9](https://github.com/d0k3/GodMode9/releases/latest)
* 最新版的[3DSident](https://github.com/joel16/3DSident/releases/latest)
* 最新版的[dgTool](https://github.com/Plailect/dgTool/releases/latest)
* 自制程序[新手包](http://smealum.github.io/ninjhax2/starter.zip)
* 适合你**目标3DS**版本的NFIRM压缩包
  + [新3DS 11.0.0](magnet:?xt=urn:btih:2d13a5ea1570f911bd5c6423e0c30e51d548837a&dn=11.0.0%5Fto%5F10.4.0%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)
  + [老3DS 11.0.0](magnet:?xt=urn:btih:72393bbd99bc285db84a9cabf39d9b3200058d6a&dn=11.0.0%5Fto%5F10.4.0%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  ~    
  + [新3DS 11.1.0](magnet:?xt=urn:btih:d7d60c27c18f53bd8508a194656a465f6448bedf&dn=11.1.0%5Fto%5F10.4.0%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  + [老3DS 11.1.0](magnet:?xt=urn:btih:0caf9a948a2d8bf23606d641f6628e2baeb983bb&dn=11.1.0%5Fto%5F10.4.0%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  ~        
  + [新3DS 11.2.0](magnet:?xt=urn:btih:881388a552a1ce9a963d391bf1a023642270991c&dn=11.2.0%5Fto%5F10.4.0%5Fn3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)     
  + [老3DS 11.2.0](magnet:?xt=urn:btih:a479e4ee55efbc18c181d426cd77a34815388151&dn=11.2.0%5Fto%5F10.4.0%5Fo3ds.zip&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=http%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fzer0day.ch%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969%2Fannounce&tr=http%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2Fexplodie.org%3A6969%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2710%2Fannounce&tr=udp%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=http%3A%2F%2Fp4p.arenabg.com%3A1337%2Fannounce&tr=udp%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker.aletorrenty.pl%3A2710%2Fannounce&tr=http%3A%2F%2Ftracker1.wasabii.com.tw%3A6969%2Fannounce&tr=http%3A%2F%2Ftracker.baravik.org%3A6970%2Fannounce&tr=http%3A%2F%2Ftracker.tfile.me%2Fannounce&tr=udp%3A%2F%2Ftorrent.gresille.org%3A80%2Fannounce&tr=http%3A%2F%2Ftorrent.gresille.org%2Fannounce&tr=udp%3A%2F%2Ftracker.yoshi210.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.tiny-vps.com%3A6969%2Fannounce&tr=udp%3A%2F%2Ftracker.filetracker.pl%3A8089%2Fannounce)    
* 如果**目标3DS**的系统版本低于11.2.0，你_还_需要：
  + 最新版的[ctr-httpwn](https://github.com/yellows8/ctr-httpwn/releases/latest)

#### 操作指南

##### 第一部分 - 准备工作

使用一个[存档管理器](https://github.com/J-D-K/JKSM/releases/latest)，备份目标3DS上（它会被格式化！）你觉得重要的存档。
{: .notice--warning}

1. 在**来源3DS**的SD卡根目录下，新建一个名为`files9`的文件夹（如果不存在的话）
2. 解压`GodMode9`压缩包，复制`GodMode9.bin`到你SD卡的`/luma/payloads/`目录下，并重命名`GodMode9.bin`为`up_GodMode9.bin`
3. 复制DSiWare注入包中的`.app`文件到**来源3DS**的SD卡根目录下
4. 复制DSiWare注入包中的`savedata`文件夹到**来源3DS**的SD卡根目录下
4. 将**来源3DS**的SD卡插回
5. 在**来源3DS**上，按住(Start)键启动，运行Hourglass9
6. 进入`SysNAND Options`，选择`SysNAND Backup/Restore`，备份**（最小大小）**SysNAND到`NANDmin.bin`
7. 在主菜单按(Select)键，弹出**来源3DS**的SD卡，并插入电脑中
8. 复制`/files9/`文件夹下的`NANDmin.bin`和`NANDmin.bin.sha`文件到一个安全的位置
  + 在多个位置进行备份
  + 备份文件可以在将来出现错误时将你的机器救砖
  + **你的备份文件应该符合[这个](nand-size)页面上列出的大小。如果不是，你应该删除它并重新做一次！**
9. 将**目标3DS**的SD卡插入电脑中
10. **将两台3DS的SD卡上的所有文件分别备份到电脑上两个分开的文件夹中（标记好哪个是哪个！）**
11. 将两张SD卡插回对应的3DS中
12. 按（Start）键重启

##### 第二部分 - 备份DSiWare

完成整个教程后，你可以通过从系统内存中删除DSiWare，再从SD卡中恢复备份文件，恢复你的DSiWare存档
{: .notice--info}

备份文件仅能用于当前的NAND。如果你格式化了你的3DS，或者从NAND备份中恢复（特别是如果`movable.sed`曾被修改过），它将不再可用。
{: .notice--info}

1. 在**来源3DS**上，进入系统设置，选择"Data Management"（数据管理），然后选"DSiWare"
2. 将SD卡上任何已有的DSiWare游戏复制回System Memory
3. 将你想使用的DSiWare游戏复制到SD卡
4. 退出系统设置

##### 第三部分 - 注入游戏和存档

1. 按住(方向上)键开机，进入GodMode9
2. 选择`SDCARD`
3. 在DSiWare注入`.app`文件上，按(Y)键复制它
4. 按(B)键返回到主菜单
5. 依次选择`SYSNAND TWLN` -> `title` -> `00030004` -> `(8位ID)`
  + 请参照[DSiWare列表](dsiware-list)页面查找所用游戏的8位ID
6. 选择`content`
7. 在目录下`.app`文件上按(A)键
8. 选择"Inject data @offset"（在位移处注入数据）
9. 按(A)键选择offset（位移）`00000000`
10. 按(A)键确定解锁SysNAND写入，输入屏幕提示的组合键
11. 按(B)键返回到主菜单
12. 依次选择`SYSNAND TWLN` -> `title` -> `00030004` -> `(8位ID)`
  + 请参照[DSiWare列表](dsiware-list)页面查找所用游戏的8位ID
13. 选择`data`
14. 在`public.sav`文件上按(A)键
15. 选择"Mount as FAT image"（作为FAT镜像加载）
  + 如果你没有看到这个选项，确保你使用的是最新提交（commit）的GodMode9，而非最新的发布版（release）
  + 如果你还是没有看到这个选项，请[提交这个bug](https://github.com/d0k3/GodMode9/issues)
19. 这将使你回到主菜单
20. 选择`SDCARD`
13. 在`savedata`文件夹中的文件上按(Y)键复制它们
  + 如果在`savedata`文件夹里还有一个`savedata`文件夹，这不是错误。你应该复制第二个`savedata`文件夹，而不是里面的文件
14. 按(B)键返回主菜单
15. 选择`FAT IMAGE`
17. 按(X)键删除`FAT IMAGE`里面的所有文件
16. 按(Y)键，将`savedata`文件夹**里面的文件**复制到`FAT IMAGE`下
17. 选择"Copy path(s)"
18. 按(A)键解锁镜像写入，输入屏幕提示的组合键
19. 按(Start)键重启
20. 在**来源3DS**上运行你的DSiWare游戏
21. 点击屏幕或按任意键开始游戏，测试游戏存档是否工作
  + 如果你使用的是欧版文件（**Legends of Exidia**，Exidia传奇），在两个标题界面按(A)键或(Start)键，选择第一个存档并点继续
  + 如果你的游戏报有关`boot.nds`的错误或出现白屏，说明**漏洞已被成功利用**
  + 如果你的游戏报错提示存档损坏或不能访问，请确认你复制的是`savedata`文件夹**里面的文件**，而非`savedata`文件夹本身
  + 如果你的游戏正常进行，没有报有关`boot.nds`的错误或出现白屏，你应该立刻停止，找一下哪里出了问题
  + 如果出现黑屏，[参见这个问题排查](troubleshooting#twl_broken)
  + 如果在**目标3DS**上没有这个游戏，或报错提示存档损坏或不能访问，[参见这个问题排查](troubleshooting#ts_dsiware)

##### 第四部分 - ctr-httpwn

**本部分仅在你的_目标3DS_系统版本低于11.2.0时才需要进行**

**本部分可以使你转移非最新版本的系统**

1. 解压ctr-httpwn压缩包，复制`3ds`文件夹，覆盖到**目标3DS**的SD卡根目录
2. 将你的SD卡插回**目标3DS**
2. 在3DS上，依照[自制程序启动器（无浏览器）](homebrew-launcher-(no-browser))一节进入自制程序启动器
  + **系统版本是10.7.0和11.0.0的新3DS可以选择依照[自制程序启动器（浏览器）](homebrew-launcher-(browser))一节进入**
  + **确保menuhax没有安装，否则你将无法从自制程序启动器返回到桌面菜单（Home Menu）**
3. 在**目标3DS**上运行ctr-httpwn
4. 按(A)键继续
5. 按(Start)键退出ctr-httpwn
6. 按(Start)键打开自制程序启动器的退出菜单
7. 按(X)键返回到桌面菜单（不重启）
  + 你可能会看到"Error has occurred"信息，并提示继续。没关系，直接按(A)键
8. 进入下一节而**不要重启**
  + **目标3DS**已被暂时打了补丁，在不运行最新版本系统的情况下开启了网络功能（例如系统传输）
  + 请注意退出系统设置将会重启系统
  + 如果系统重启，你需要再运行一次ctr-httpwn才能使系统传输生效

##### 第五部分 - 系统传输

1. **将两台3DS的SD卡上的所有文件分别备份到电脑上两个分开的文件夹中（标记好哪个是哪个！）**
2. 将两张SD卡插回各自对应的3DS
4. 如果**目标3DS**上已经登录了任天堂网络ID（NNID），你必须在系统设置里面格式化设备：
  + 选择"Other Settings"（其它设置）里面的最后一页，选择"Format System Memory"（格式化系统内存），然后按提示操作
5. 请阅读以下注意事项：
  + 你的自制系统的3DS = 来源3DS = "Source System"（来源系统）
  + 你的原生系统3DS = 目标3DS = "Target System"（目标系统）
  + **如果提示，请迁移DSiWare titles！**
  + 如果提示，**不要**删除来源系统上的SD内容
  + 确保在进行系统转移的时候，两台3DS的电池都有电
  + 仅限2DS/老3DS（来源）转移到新3DS（目标）- 如果被问到使用何种方式转移SD卡上的数据：
    + **不要**选择"Low-Capacity microSD Card Transfer"（低容量microSD卡迁移）或minimal option（最小迁移，选项2），因为这将只转移tickets，可能不会转移DSiWare的存档。
    + 快速的方法：如果你能自己将来源SD卡的数据移动到目标SD卡，当提示时选择"PC-Based Transfer"（电脑端迁移，选项3）。
    + 最慢的方法：如果你不能自己在电脑上迁移SD卡数据，选择**full** "Wireless Transfer"（完整无线迁移，选项1）。
6. 进入[这个链接](http://en-americas-support.nintendo.com/app/answers/detail/a_id/227/)，按照任天堂的官方操作指南进行系统迁移。记住你刚才读的注意事项。

##### 第六部分 - 恢复来源3DS

1. 在**来源3DS**上，完成初始化的操作
2. 进行如下操作
    + 在**目标3DS**上完成本教程后面的部分，然后等一个礼拜，再从**目标3DS**迁移回**来源3DS** *（请记住，你不能从一个新3DS迁移回一个老3DS）*
    + 给任天堂打电话，告诉它们你访问不了你当前NNID绑定的设备（也就是**目标3DS**），想把它绑到另一台设备上（也就是**来源3DS**）（译者注：真是对大陆玩家的实力嘲讽）
    + 你也可以参照[移除NNID](https://3ds.guide/troubleshooting#rm_nnid) 页面，移除**来源3DS**上的NNID，如果你希望它留在**目标3DS**上
3. 按(Start)键重启**来源3DS**，运行Hourglass9
4. 进入`SysNAND Backup/Restore`选项，选择`NANDmin.bin`文件恢复SysNAND

##### 第七部分 - 备份目标3DS的NFIRM

1. 复制dgTool `boot.nds`到**目标3DS**的SD卡根目录
1. 在**目标3DS**的SD卡根目录新建一个名为`dgTool`的文件夹，如果它还不存在的话
3. 解压缩NFIRM的压缩包，复制文件到**目标3DS**SD卡的o`dgTool`文件夹下
3. 在**目标3DS**上运行你的DSiWare游戏
4. 开始你的DSiWare游戏，运行dgTool
  + 如果游戏没有运行dgTool，[参见这个问题排查](troubleshooting#ts_dsiware)
5. 选择"Dump f0f1"，备份**目标3DS**的NFIRM
  + 这一步需要一些时间
6. 记下NFIRM的备份位置
7. 退出dgTool
  + 你可能需要按电源键强制关机
8. 将SD卡插回你的电脑，复制`F0F1_N3DS.bin`或`F0F1_O3DS.bin`（取决于你的设备）到一个安全的地方
  + 在多个位置进行备份
  + 备份文件可以在将来出现错误时将你的机器救砖


##### 第八部分 - 向目标3DS刷入NFIRM

**永远不要在一个已经安装了arm9loaderhax的设备上使用dgTool进行降级，否则你的设备将变砖！**

1. 在**目标3DS**上运行你的DSiWare游戏
2. 开始你的DSiWare游戏，运行dgTool
3. 选择"Downgrade FIRM to 10.4"并确认，将10.4.0 NFIRM bin刷入**目标3DS**
4. 退出dgTool
  + 你可能需要按电源键强制关机
5. 重启

##### 第九部分 - 漏洞确认

1. 解压缩3DSident压缩包，复制其中的`3ds`文件夹，与你**目标3DS**SD卡上的对应文件夹合并。
2. 将SD卡插回**目标3DS**
3. 使用[自制程序启动器（无浏览器）](homebrew-launcher-(no-browser))一节的方法，在你的**目标3DS**上运行自制程序启动器
4. 运行3DSident
5. 验证以下信息是否正确：
  + **Kernel version（内核版本）**: 2.50-11
  + **FIRM version（固件版本）**: 2.50-11
  + 如果其中任何一个没有显示如上所示的版本号，确保你使用的是正确的NFIRM压缩包，然后尝试重新刷入NFIRM

你的**目标3DS**在系统设置中的版本号*不会*变更。
{: .notice--info}

进入[Decrypt9（自制程序启动器）](decrypt9-(homebrew-launcher))继续教程
{: .notice--primary}
