---
title: "Decrypt9（自制程序启动器）"
permalink: /decrypt9-(homebrew-launcher).html
---

因为有一个bug，safehax需要一个能正常工作的卡带（3ds，nds，闪存卡带，等等）插入机器才能成功。作为一个临时解决方案，系统版本在9.2.0及以下的用户可以无需卡带，直接拷贝`Decrypt9WIP.3dsx`到`/3ds/`下，无需破解即可运行。
{: .notice--info}

#### 你需要

* 最新版本的[Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/)
* 最新版本的[safehax+fasthax](https://gbatemp.net/attachments/safehax-fasthax-cb6a1bc-zip.73592/)

#### 操作指南

1. 在SD卡根目录下创建`files9`文件夹（如果没有的话）
2. 解压缩safehax+fasthax压缩包，复制其中的文件到你的SD卡根目录，覆盖已有文件
3. 复制Decrypt9WIP压缩包中的`Decrypt9WIP.bin`文件到你SD卡根目录下，重命名`Decrypt9WIP.bin`为`arm9.bin`
3. 将SD卡重新插入你的3DS
4. 进入自制程序启动器
4. 运行safehax
5. 如果漏洞利用成功，你将进入Decrypt9

继续进行[2.1.0 ctr迁移](2.1.0-ctrtransfer)    
{: .notice--primary}
