---
title: "F3 (Linux)"
permalink: /f3-(linux).html
lang: zh_CN
ref: f3-(linux)
---

本节教程将带你使用F3检查SD卡错误。
{: .notice}

本节操作可能需要数小时的时间，取决于你的SD卡大小和你电脑的速度！
{: .notice--info}

本节教程仅限Linux用户。如果你的操作系统不是Linux，参见[H2testw (windows)](h2testw-(windows))或[F3X (mac)](f3x-(mac))页面。
{: .notice--info}

#### 你需要

* 最新版的[F3](https://github.com/AltraMayor/f3/releases/latest)

#### 操作指南

1. 解压缩f3的压缩包
2. `cd`进入f3的文件夹
3. 在terminal中执行`make`命令，编译F3
4. 将SD卡插入电脑
5. 加载你的SD卡
6. 执行：`./f3write <your sd card mount point>` （译者注：sd card mount point即sd卡挂载的位置）
7. 等待执行结束。下面是一个执行结果样例。

		$ ./f3write /media/michel/6135-3363/
		Free space: 29.71 GB
		Creating file 1.h2w ... OK!
		...
		Creating file 30.h2w ... OK!
		Free space: 0.00 Byte
		Average Writing speed: 4.90 MB/s

8. 执行：`./f3read <your sd card mount point>`
9. 等待执行结束。下面是一个执行结果样例。

		$ ./f3read /media/michel/6135-3363/
		                  SECTORS      ok/corrupted/changed/overwritten
		Validating file 1.h2w ... 2097152/        0/      0/      0
		...
		Validating file 30.h2w ... 1491904/        0/      0/      0

		  Data OK: 29.71 GB (62309312 sectors)
		Data LOST: 0.00 Byte (0 sectors)
			       Corrupted: 0.00 Byte (0 sectors)
			Slightly changed: 0.00 Byte (0 sectors)
			     Overwritten: 0.00 Byte (0 sectors)
		Average Reading speed: 9.42 MB/s


如果测试结果为`Data LOST: 0.00 Byte (0 sectors)`，你的SD卡是好的，删除你SD卡上所有的`.h2w`文件
{: .notice--success}

如果测试结果为其它内容，你的SD卡可能已损坏，你可能得换一张了！
{: .notice--danger}

返回到[开始教程](get-started)
{: .notice--primary}
