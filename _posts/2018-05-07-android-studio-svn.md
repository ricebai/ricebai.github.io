---
layout:     post
title:      TortoiseSVN
subtitle:   TortoiseSVN 下载安装和使用
date:       2018-05-02
author:     ricebai
header-img: img/posts/svn/post-bg-svn.png
catalog: true
tags:
    - Android Studio
    - SVN
---

## SVN 下载与配置

首先我们要确认是否已经安装 `SVN`，如果没有安装点击 [下载](https://www.visualsvn.com/server/download/)。

如果已经下载安装完毕，则需要在安装目录中找到 `snv.exe`。

![svn-exe](https://ricebai.github.io/img/posts/svn/svn-exe.jpg)

没有找到 `svn.exe` 的需要重新运行安装包，修复svn。

![svn](https://ricebai.github.io/img/posts/svn/svn.jpg)


### 配置 SVN

打开 Android Studio，File - Settings - Version Control - Subversion，配置 `svn.exe`。

![svn-set](https://ricebai.github.io/img/posts/svn/svn-set.jpg)

### 使用 SVN

打开 Android Studio，菜单中选择 Subversion。

![svn-menu](https://ricebai.github.io/img/posts/svn/svn-menu.jpg)

添加 SVN 地址，填写用户名与密码，建议勾选 `Save credentials`，点击 `ok`，点击 `Checkout`。

![svn-add](https://ricebai.github.io/img/posts/svn/svn-add.jpg)

选择导出目录。

![svn-checkout](https://ricebai.github.io/img/posts/svn/svn-checkout.jpg)

选择导出 `JAVA` 版本

![svn-v](https://ricebai.github.io/img/posts/svn/svn-v.jpg)

之后只需要静静的等待即可。
