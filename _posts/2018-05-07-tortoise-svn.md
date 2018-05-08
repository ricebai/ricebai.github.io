---
layout:     post
title:      TortoiseSVN
subtitle:   TortoiseSVN 下载安装和使用
date:       2018-05-07
author:     ricebai
header-img: img/posts/svn/post-bg-svn.png
catalog: true
tags:
    - Android Studio
    - SVN
---

# SVN

SVN是Subversion的简称，是一个开放源代码的版本控制系统，相较于RCS、CVS，它采用了分支管理系统，它的设计目标就是取代CVS。互联网上很多版本控制服务已从CVS迁移到Subversion。说得简单一点SVN就是用于多个人共同开发同一个项目，共用资源的目的。

TortoiseSVN 是 Subversion 版本控制系统的一个免费开源客户端，可以超越时间的管理文件和目录。文件保存在中央版本库，除了能记住文件和目录的每次修改以外，版本库非常像普通的文件服务器。你可以将文件恢复到过去的版本，并且可以通过检查历史知道数据做了哪些修改，谁做的修改。这就是为什么许多人将 Subversion 和版本控制系统看作一种“时间机器”。

### TortoiseSVN 下载

没有安装点击下载 [TortoiseSVN](https://www.visualsvn.com/server/download/)。

如果已经下载安装完毕，则需要在安装目录中找到 `snv.exe`。

![svn-exe](https://ricebai.github.io/img/posts/svn/svn-exe.jpg)

没有找到 `svn.exe` 的需要重新运行安装包，修复svn。

![svn](https://ricebai.github.io/img/posts/svn/svn.jpg)

### Eclipse SVN

打开 Eclipse ，从菜单进入 Help - Install New Software...

![menu](https://ricebai.github.io/img/posts/svn/svn-eps-menu.jpg)

#### 导入svn插件jar/zip

选中导入svn包。

![add-jar](https://ricebai.github.io/img/posts/svn/svn-eps-addjar.jpg)

勾选 svn 插件列表，点击 next。

![add-jar](https://ricebai.github.io/img/posts/svn/svn-eps-addjar2.jpg)

### Android Studio SVN

#### SVN 配置

打开 Android Studio，File - Settings - Version Control - Subversion，配置 `svn.exe`。

![svn-set](https://ricebai.github.io/img/posts/svn/svn-ads-set.jpg)

#### SVN 使用

打开 Android Studio，菜单中选择 Subversion。

![svn-menu](https://ricebai.github.io/img/posts/svn/svn-ads-menu.jpg)

添加 SVN 地址，填写用户名与密码，建议勾选 `Save credentials`，点击 `ok`，点击 `Checkout`。

![svn-add](https://ricebai.github.io/img/posts/svn/svn-ads-add.jpg)

选择导出目录。

![svn-checkout](https://ricebai.github.io/img/posts/svn/svn-ads-checkout.jpg)

选择导出 `JAVA` 版本，完成导出。

![svn-v](https://ricebai.github.io/img/posts/svn/svn-ads-v.jpg)

#### SVN update 、commit 等操作。

![svn-ads-opts](https://ricebai.github.io/img/posts/svn/svn-ads-opts.jpg)
