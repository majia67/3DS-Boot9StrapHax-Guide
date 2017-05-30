---
title: "H2testw (Windows)"
---

本节是一个附加章节，将指导你使用F3X检查SD卡错误。
{: .notice}

本节操作可能需要数小时的时间，取决于你的SD卡大小和你电脑的速度！
{: .notice--info}

本节教程仅限Windows用户。如果你的操作系统不是Windows，参见[F3X (mac)](f3x-(mac))或[F3 (Linux)](f3-(linux))页面。
{: .notice--info}

#### 你需要

* 最新版本的[h2testw](http://www.heise.de/ct/Redaktion/bo/downloads/h2testw_1.4.zip)

#### 操作指南

1. 解压缩h2testw压缩包，复制`h2testw.exe`文件到桌面
2. 将SD卡插入电脑
3. 运行`h2tsetw.exe`
4. 选择"English"（译者注：如果有中文也可以选中文）
5. 点击"Select target"（选择目标）
6. 选择你SD卡对应的盘符
7. 确保"all available space"（所有可用空间）已勾选
8. 点击"Write + Verify"
9. 等待测试完成

---

如果测试结果显示`Test finished without errors`（测试完成，没有错误），你的SD卡是好的，删除你SD卡上所有的`.h2w`文件
{: .notice--success}

如果测试结果为其它内容，你的SD卡可能已损坏，你可能得换一张了！
{: .notice--danger}

返回到[开始教程](get-started)
{: .notice--primary}
