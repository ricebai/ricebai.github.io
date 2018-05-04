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


## 前言

*工欲善其事，必先利其器*，一款好的开发工具是提升工作效率的首要选择。🙊

### 下载Atom：

传送门：[atom.io 官网连接](https://atom.io) 支持 Windows 版本和 Mac 版本。

#### Atom 主题修改

打开 *Atom* ，File - Settings - Themes 设置主题

![themes](https://ricebai.github.io/img/posts/atom-github/settings-themes.jpg)

#### Atom 插件安装和卸载

打开 *Atom* ，File - Settings - Install 查找插件，Install 安装插件

![install](https://ricebai.github.io/img/posts/atom-github/settings-install.jpg)

打开 *Atom* ，File - Settings - Packages 设置、卸载、禁用插件

网络搜索插件：[https://atom.io/packages/](https://atom.io/packages/)

其他推荐：

##### 1.  [使用 Sync-settings 插件，Atom 的备份神器](https://ricebai.github.io/2018/04/22/Atom-Sync)

##### 2.  [Atom各种有用的插件](https://www.jianshu.com/p/041d3d5f3997)

### [Markdown](https://ricebai.github.io/2018/04/20/Markdown-Readme/) 的使用

#### 推荐 Markdown 插件：

1. **language-markdown** 代码着色和快速创建代码片段
2. **markdown-scroll-sync** 同步预览 markdown 页面十分方便
3. **markdown-table-editor** 快速创建表格

#### 打开 Markdown 预览

打开 *Atom* ，Packages - Markdown Preview - Toggle Preview

![view](https://ricebai.github.io/img/posts/atom-github/markdown-view.jpg)
#### 七牛云图：

[如何利用 Atom 打造一个带有便捷图床功能的 Markdown 编辑器](https://www.jianshu.com/p/af4d34d39797)

<a id="atom"></a>

### 使用GitHub

Atom 官网也有操作描述，[github.atom.io](https://github.atom.io/).

![options](https://ricebai.github.io/img/posts/atom-github/atom-opts.jpg)

#### 安装 Git

[Git Dwonload](https://git-scm.com/downloads)

#### 配置 SSH

[（Git 学习）Git SSH Key 创建步骤](https://segmentfault.com/a/1190000009567424)

> 如果 ssh 如下图错误，配置ssh重来一遍

![ssh](https://ricebai.github.io/img/posts/atom-github/git-ssh-error.jpg)

### Atom `commit` & `push` 错误

#### Please tell me...

这个问题好处理，按照它的提示，在 `Git` 中运行命令：

```
git config --global user.email '你的邮箱'
git config --global user.name ‘你的名字’
```

> 这需要运行 git 添加用户名和邮箱

![account](https://ricebai.github.io/img/posts/atom-github/atom-act.jpg)

#### Atom 403 错误

如果你遇到下图提示，Atom 403 错误，恭喜你找到了解决方法。

![403](https://ricebai.github.io/img/posts/atom-github/atom-403.jpg)

我们先打开已经安装好的 [GitHub Desktop](https://desktop.github.com/)，点击菜单 File - Optios - Advanced

*External editor* 选择 Atom

![advanced](https://ricebai.github.io/img/posts/atom-github/advanced.jpg)

在 GitHub Desktop 菜单，选择 Repository - Open in Atom ,这时在 Atom 中的 `push` 操作就好了

看到这里还不知道怎么 `commit`、`push` ? [传送门-送你回去再看一遍](#atom)

### 总结

通过 `GitHub Desktop` 工具打开 `Atom` 可以直接使用 Atom 的 `commit`、`push` 操作。
而安装 `Git` 呢，能使用 `Git` 命令操作 GitHub 而已。
