---
layout:     post
title:      Atom & GitHub
subtitle:   Atom 中使用 GitHub，打造属于自己的 GitHub 编辑器
date:       2018-04-21
author:     ricebai
header-img: img/posts/atom-github/post-bg-atom.png
catalog: true
tags:
    - Markdown
    - GitHub
    - Atom
---


# Atom

*工欲善其事，必先利其器*，一款好的编辑工具是提升工作效率的首要选择。🙊

推荐使用一款非常不错的编辑器 `Atom` 和 `Sublime Text` 有些相似。

Atom 是 `GitHub` 专门为程序员推出的一个跨平台文本编辑器。具有简洁和直观的图形用户界面，并有很多有趣的特点：支持CSS，HTML，JavaScript等网页编程语言。它支持宏，自动完成分屏功能，集成了文件管理器。

## 下载和使用

### 下载
传送门：[atom.io 官网连接](https://atom.io) 支持 Windows 版本和 Mac 版本。

### 主题修改

打开 *Atom* ，File - Settings - Themes 设置主题

![themes](https://ricebai.github.io/img/posts/atom-github/settings-themes.jpg)

### 插件安装和卸载

打开 *Atom* ，File - Settings - Install 查找插件，Install 安装插件

![install](https://ricebai.github.io/img/posts/atom-github/settings-install.jpg)

打开 *Atom* ，File - Settings - Packages 设置、卸载、禁用插件

也可以通过网络搜索插件下载安装 [https://atom.io/packages/](https://atom.io/packages/)

#### Sync-Settings

当在多台电脑使用 Atom 时十分方便的一个插件，[Sync-settings](https://ricebai.github.io/2018/04/22/atom-sync) 备份神器，能自动同步 Atom 设置和插件。

#### Markdown

在需要编写 [Markdown](https://ricebai.github.io/2018/04/20/markdown-readme/) 文章时，推荐几款提升效率的插件。

- **language-markdown** 代码着色和快速创建代码片段
- **markdown-scroll-sync** 同步预览 markdown 页面十分方便
- **markdown-table-editor** 快速创建表格

#### Markdown 预览

打开 *Atom* ，Packages - Markdown Preview - Toggle Preview

![view](https://ricebai.github.io/img/posts/atom-github/markdown-view.jpg)

#### 七牛云图：

[如何利用 Atom 打造一个带有便捷图床功能的 Markdown 编辑器](https://www.jianshu.com/p/af4d34d39797)

#### 其他插件

有更多的插件推荐：[传送门](https://www.jianshu.com/p/041d3d5f3997)

<a id="atom"></a>

### 使用GitHub

Atom 官网也有操作描述，[github.atom.io](https://github.atom.io/).

![options](https://ricebai.github.io/img/posts/atom-github/atom-opts.jpg)

## 安装 Git

我们需要先下载 [Git](https://git-scm.com/downloads)，运行后进行下面配置。

### 配置 SSH

[（Git 学习）Git SSH Key 创建步骤](https://segmentfault.com/a/1190000009567424)

## 错误解答

### Git ssh 配置不成功

> 如果 ssh 如下图错误，配置ssh重来一遍

![ssh](https://ricebai.github.io/img/posts/atom-github/git-ssh-error.jpg)

### Atom `commit` & `push` 错误

***Please tell me...***

这个问题好处理，按照它的提示，在 `Git` 中运行命令：

```
git config --global user.email '你的邮箱'
git config --global user.name ‘你的名字’
```

> 这需要运行 git 添加用户名和邮箱

![account](https://ricebai.github.io/img/posts/atom-github/atom-act.jpg)

### Atom 403 错误

如果你遇到下图提示，Atom 403 错误，恭喜你找到了解决方法。

![403](https://ricebai.github.io/img/posts/atom-github/atom-403.jpg)

我们先打开已经安装好的 [GitHub Desktop](https://desktop.github.com/)，点击菜单 File - Optios - Advanced

*External editor* 选择 Atom

![advanced](https://ricebai.github.io/img/posts/atom-github/advanced.jpg)

在 GitHub Desktop 菜单，选择 Repository - Open in Atom ,这时在 Atom 中的 `push` 操作就好了

看到这里还不知道怎么 `commit`、`push` ? [传送门-送你回去再看一遍](#atom)

### 总结

通过 `GitHub Desktop` 工具打开 `Atom` 可以直接使用 Atom 的 `commit`、`push` 操作。

而安装 `Git` 呢，能使用 `Git` 命令操作 GitHub 。
