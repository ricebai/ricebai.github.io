---
layout:     post
title:      IntelliJ Tomcat Error
subtitle:   java.net.BindException "Address already in use:JVM_Bind"
date:       2019-03-11
author:     ricebai
header-img: img/posts/intellij-idea/intellij-idea-bg.png
catalog: true
tags:
    - IDEA
---
# Error 

Error Running 'Tomcat 7.0.62'

### 错误信息

Tomcat Debuger 启动 WEB 项目端口 `52177` 被占用。

![port](https://ricebai.github.io/img/posts/intellij-idea/port1.jpg)

### 解决办法

点击 `Edit Configurations...` 修改 `Port` 端口数字即可。

![port](https://ricebai.github.io/img/posts/intellij-idea/port2.jpg)

