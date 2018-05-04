---
layout:     post
title:      Android Studio
subtitle:   Android Studio 的下载和安装
date:       2018-05-02
author:     ricebai
header-img: img/posts/android-studio/post-bg-android.png
catalog: true
tags:
    - Android
    - Android Studio
---

# Android Studio

Android Studio 是一个 `Android` 集成开发工具，基于 `IntelliJ IDEA`. 类似 `Eclipse ADT`，`Android Studio` 提供了集成的 `Android` 开发工具用于开发和调试。

在IDEA的基础上，Android Studio 提供：
- 基于 `Gradle` 的构建支持
- `Android` 专属的重构和快速修复
- 提示工具以捕获性能、可用性、版本兼容性等问题
- 支持 `ProGuard` 和应用签名
- 基于模板的向导来生成常用的 `Android` 应用设计和组件
- 功能强大的布局编辑器，可以让你拖拉 UI 控件并进行效果预览

## 下载和安装

我们可以再官网下载 `Android Studio` 安装包，支持 `Windows` `Mac` `Linux` 平台工具下载。

由于我的环境是 `Windows`，下面我以 `Windows` 为例图文说明。

### 下载

浏览器访问 [Android Studio 中文社区(官网)](http://www.android-studio.org) 下载开发工具，如图：

![download android studio](https://ricebai.github.io/img/posts/android-studio/as-download.jpg)

### 安装

打开安装包，一路下一步。需要修改安装路径的中间选择下。

![install](https://ricebai.github.io/img/posts/android-studio/as-install.gif)

## Android Studio 运行

在安装完毕后直接运行 `Android Studio` 会遇到下面选择。

### 旧的安装配置文件

如果之前安装过 `Android Studio`，我们可以选择之前安装的版本配置文件。

![old-install](https://ricebai.github.io/img/posts/android-studio/as-install-old.jpg)

### 首次安装运行

第一次安装运行，我们默认选择下面这一项。后面都按第一次运行说明。

![first-install](https://ricebai.github.io/img/posts/android-studio/as-install-first.jpg)

稍作等待后，并没有迎来期待的欢迎界面，而是遇到了下面的提示。

![run](https://ricebai.github.io/img/posts/android-studio/as-run.jpg)

没有找到 `Android SDK`，我们点击 `cancel` 会自动下载一点东西。

![run](https://ricebai.github.io/img/posts/android-studio/as-cancel.jpg)

看到熟悉的欢迎界面，一路点下一步（中间有黑白主题选项，有需要的小伙伴可以在这里选择或者进入主界面单独设置）。`Finish` 后进入考验网速的时候了，`Android Studio` 会自动下载 `Android SDK`。

![run](https://ricebai.github.io/img/posts/android-studio/as-start.gif)

经过漫长的等待，就能进入真正的工作界面。

![welcome](https://ricebai.github.io/img/posts/android-studio/as-welcome.jpg)
