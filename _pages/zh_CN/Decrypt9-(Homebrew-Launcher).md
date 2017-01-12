---
title: "Decrypt9（自制程序启动器）"
permalink: /decrypt9-(homebrew-launcher).html
lang: zh_CN
ref: decrypt9-(homebrew-launcher)
---

#### 你需要

* 最新版本的[Decrypt9WIP](https://github.com/d0k3/Decrypt9WIP/releases/)
* 最新版本的[safehax](https://github.com/TiniVi/safehax/releases/latest)
* 最新版本的[fasthax](https://github.com/nedwill/fasthax/releases/latest)

#### 操作指南

1. 在SD卡根目录下创建`files9`文件夹（如果没有的话）
2. 复制`safehax.3dsx`文件到你的SD卡的`/3ds/`目录下
3. 复制`fasthax.3dsx`文件到你的SD卡的`/3ds/`目录下
4. 复制Decrypt9WIP压缩包中的`Decrypt9WIP.bin`文件到你SD卡根目录下，重命名`Decrypt9WIP.bin`为`safehaxpayload.bin`
5. 将SD卡重新插入你的3DS
6. 进入自制程序启动器
7. 运行fasthax
8. 运行结束后，按(Start)键退出，返回到自制程序启动器
  + 可能需要多试几次
9. 运行safehax
10. 如果漏洞利用成功，你将进入Decrypt9

继续进行[2.1.0 ctr迁移](2.1.0-ctrtransfer)    
{: .notice--primary}
