---
layout:     post
title:      Eclipse SVN
subtitle:   Eclipse SVN 使用和安装的几种方法
date:       2018-05-08
author:     ricebai
header-img: img/posts/svn/post-bg-svn.png
catalog: true
tags:
    - Eclipse
    - SVN
---

# Eclipse SVN

安装 Eclipse SVN 插件可以方便的在 Eclipse 内部使用 SVN 功能。

### Marketplace 下载

打开Eclipse --> Help --> Eclipse Marketplace --> 在Find中输入subclipse搜索 --> 找到subclipse点击install

![subclipse](http://img.blog.csdn.net/20150102214602244?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdjEyMzQxMTczOQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)


### Install New Software 下载

打开Eclipse --> Help --> Install New Software --> 点击add按钮，输入下载地址：http://subclipse.tigris.org/update_1.10.x，点击OK

![rp](http://img.blog.csdn.net/20150102215010737?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdjEyMzQxMTczOQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)

将Subclipse和SVNKit打勾后，一路next或agree到结束即可

![](http://img.blog.csdn.net/20150102215204461?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdjEyMzQxMTczOQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)

### site zip 导入

zip 导入的话，我们首先要准备好 [svn 插件](http://subclipse.tigris.org/servlets/ProjectDocumentList?folderID=2240)。

选择交新的稳定版本下载。

![svn-site-zip.jpg](../img/posts/svn/svn-site-zip.jpg)

#### 通过配置添加 site

打开 Eclipse ，从菜单进入 Help - Install New Software...

![menu](https://ricebai.github.io/img/posts/svn/svn-eps-menu.jpg)

选中导入svn包。

![add-jar](https://ricebai.github.io/img/posts/svn/svn-eps-addjar.jpg)

勾选 svn 插件列表，点击 next。

![add-jar](https://ricebai.github.io/img/posts/svn/svn-eps-addjar2.jpg)

#### 拷贝到文件添加 site

解压缩后在eclipse目录下找到dropins文件夹，进入dropins文件夹并新建一个文件夹名为svn，将features和plugins文件夹复制到svn目录下-->重启下Eclipse即可

![](http://img.blog.csdn.net/20151014092037626?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)


### SVN 的使用

https://www.cnblogs.com/liangguangqiong/p/7965770.html
