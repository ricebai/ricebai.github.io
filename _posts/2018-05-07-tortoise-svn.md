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

### TortoiseSVN 安装程序下载

没有安装点击下载 [TortoiseSVN](https://www.visualsvn.com/server/download/)。

如果已经下载安装完毕，则需要在安装目录中找到 `snv.exe`。因为部分开发工具要设置使用。

![svn-exe](https://ricebai.github.io/img/posts/svn/svn-exe.jpg)

没有找到 `svn.exe` 的需要重新运行安装包，修复svn。

![svn](https://ricebai.github.io/img/posts/svn/svn.jpg)

### Eclipse SVN

#### Marketplace 下载

打开Eclipse - Help - Eclipse Marketplace - 在Find中输入subclipse搜索 --> 找到subclipse点击install

打开 Eclipse ，从菜单进入 Help - Install New Software...

![menu](https://ricebai.github.io/img/posts/svn/svn-eps-menu.jpg)

#### Install New Software 下载

打开Eclipse - Help - Install New Software - 点击add按钮，输入下载地址：

[http://subclipse.tigris.org/update_1.10.x](http://subclipse.tigris.org/update_1.10.x)，点击OK

将Subclipse和SVNKit打勾后，一路next或agree到结束即可

#### 导入svn插件 site.zip

zip 导入的话，我们首先要准备好 [svn 插件](http://subclipse.tigris.org/servlets/ProjectDocumentList?folderID=2240)。

选择交新的稳定版本下载。

![svn-site-zip.jpg](https://ricebai.github.io/img/posts/svn/svn-site-zip.jpg)

打开 Eclipse ，从菜单进入 Help - Install New Software...

![menu](https://ricebai.github.io/img/posts/svn/svn-eps-menu.jpg)

选中导入svn包。

![add-jar](https://ricebai.github.io/img/posts/svn/svn-eps-addjar.jpg)

勾选 svn 插件列表，点击 next。

![add-jar](https://ricebai.github.io/img/posts/svn/svn-eps-addjar2.jpg)

#### 拷贝到文件添加 site

解压缩后在eclipse目录下找到dropins文件夹，进入dropins文件夹并新建一个文件夹名为svn，将features和plugins文件夹复制到svn目录下-->重启下Eclipse即可

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
