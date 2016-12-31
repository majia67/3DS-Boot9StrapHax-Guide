---
title: "自制程序启动器（浏览器）"
permalink: /homebrew-launcher-(browser).html
---

Homebrew Launcher（自制程序启动器，HBL）有很多进入或运行方法。最常用的是browserhax（浏览器漏洞），只需使用系统内置的浏览器就能启动HBL。
{: .notice--info}

**浏览器漏洞仅支持 欧版 / 日版 / 美版 / 韩版 的机器！**
{: .notice--warning}

#### 你需要

+ 自制程序[新手包](http://smealum.github.io/ninjhax2/starter.zip)
+ 3DS已设置好互联网连接

{::comment}
+ [`config.zip`](images/config.zip)
+ The [ropbin](https://smealum.github.io/3ds/#otherapp) matching your 3DS's version
{:/comment}

#### 操作指南

##### 第一部分 -  准备工作

1. 将`starter.zip`压缩包中的`starter`文件夹下的所有文件拷贝到你SD卡的根目录
4. 将SD卡插回你的3DS

{::comment}
2. Copy the contents of `config.zip` to the `/3ds/menuhax_manager/` folder on your SD card
3. Create a folder named `menuhax` on the root of your SD card if it does not already exist
4. Rename the ropbin to `menuhaxmanager_input_payload.bin`
5. Copy `menuhaxmanager_input_payload.bin` to the `/menuhax/` folder on your SD card
{:/comment}

##### 第二部分 -  跳过版本检测

**只有系统版本在9.9.0至10.6.0需要执行本部分操作**

2. 打开主题菜单，将你的主题更换到任意一个其它主题，然后再改回来。这将初始化需要用到的主题数据
3. 打开`Settings`（设置）程序
4. 将日期改到`January 1, 2000`（2000年1月1日）
5. 将时间改到`00:00`
6. 运行浏览器，以最快的速度开启`browser settings`（浏览器设置）
7. 以最快的速度将右边滑块移到最下方，并点击Initialize Savedata（初始化缓存）（也可能叫Clear All Save Data，清除所有缓存）

##### 第三部分 -  屏蔽conntest.nintendowifi.net

**只有系统版本在10.7.0至11.0.0的新3DS需要执行本部分操作**

**本部分操作对日版机器无效**

另参见[这里](https://github.com/Plailect/Guide/issues/684)
{: .notice--info}

1. 先不要屏蔽网站，在3DS上建立互联网连接
2. 将3DS关机
3. 下载符合你3DS版本的[ropbin](https://smealum.github.io/3ds/#otherapp)
4. 将文件重命名为`browserhax_hblauncher_ropbin_payload.bin`，并拷贝到你SD卡的根目录
4. 在你的**路由器**中添加以下防火墙规则:
    + 屏蔽网站的具体做法请参考你的路由器的使用说明
    + 请务必在**路由器**中屏蔽网站。使用Windows防火墙（或其它本地防火墙）无效。
    + 将`conntest.nintendowifi.net`这一网址屏蔽，或屏蔽所有来自`69.25.139.140`这一IP地址的TCP和UDP请求
5. 启动3DS

##### 第四部分 -  浏览器漏洞（browserhax）

8. 在3DS浏览器中访问`http://yls8.mtheall.com/3dsbrowserhax_auto.php`
    + 你还可以通过扫描二维码的方式进入(在桌面菜单按(L + R)，然后点击下屏幕上的二维码图标)     
![browserhax_auto](http://yls8.mtheall.com/3dsbrowserhax_auto_qrcode.png)
    + 遇过遇到错误，参见[问题排查](troubleshooting#ts_browser)
9. 你的3DS应该开始加载自制程序菜单了
    + 如果你在第三部分里屏蔽了conntest.nintendowifi.net（或IP地址），进入自制程序菜单后请解除屏蔽

##### 第五部分 -  菜单漏洞（menuhax）

10. 打开menuhax_manager程序
11. 按A键开始安装，可能会有一些错误信息，不过只要最后出现了"Install finished successfully"就没有问题。
    + 如果弹出了"override the detected system version," 按(B)取消
12. 返回 menuhax_manager 主菜单，然后选择"Configure menuhax"
13. 按A键继续，然后选择"Type1"
14. 按住十字下键 ，然后点击触摸屏；这是推荐的运行 menuhax 的按键，因为不会和接下来教程用到的任何软件或功能相冲突
15. 返回menuhax_manager主菜单，然后按B键，接着按(Start)键退回到HBL
16. 按 (Start) 键，然后按 (A) 重启

现在你可以在系统启动时通过按十字下键来进入HBL
{: .notice--info}

如果你的系统版本在9.2.0以上，下一步请进行[降级到9.2.0](9.2.0-downgrade)
{: .notice--primary}

如果你的系统版本在9.2.0及以下，下一步请进行[Decrypt9（自制程序启动器）](decrypt9-(homebrew-launcher))
{: .notice--primary}
