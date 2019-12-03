---
layout:     post
title:      IntelliJ 导出 WAR 包
subtitle:   IntelliJ 中如何导入 WAR 包
date:       2019-03-11
author:     ricebai
header-img: img/posts/intellij-idea/intellij-idea-bg.png
catalog: true
tags:
    - IDEA
---
# WAR

war是一个可以直接运行的web模块，通常用于网站，打成包部署到容器中。以Tomcat来说，将war包放置在其\webapps\目录下，然后启动Tomcat，这个包就会自动解压，就相当于发布了。

### 设置

工具栏右上角点击设置按钮，打开设置界面
![open_setting](https://ricebai.github.io/img/posts/war/open_seting.jpg)

### 添加 Artifacts

选择 `Arifacts` ，点击 `+` 
![add_archive](https://ricebai.github.io/img/posts/war/add_archive.jpg)

设置 `name` WAR包名称和保存路径，我这里放在c:\demo\ 文件夹中。
![artifacts](https://ricebai.github.io/img/posts/war/artifacts.jpg)

build 按下图操作
![build_arifacts](https://ricebai.github.io/img/posts/war/build_arifacts.jpg)


![build](https://ricebai.github.io/img/posts/war/build.jpg)
剩下的就是静静的等到war导出完成。