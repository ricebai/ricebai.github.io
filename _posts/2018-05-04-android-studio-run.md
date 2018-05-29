---
layout:     post
title:      Android Studio 运行
subtitle:   Android Studio APP 第一次运行
date:       2018-05-04
author:     ricebai
header-img: img/posts/android-studio/post-bg-android.png
catalog: true
tags:
    - Android Studio
---

# RUN

Android Studio 运行程序。

### 运行

完成 [Android Studio 创建 ](https://ricebai.github.io/2018/05/03/android-studio-create) 后，右上角的运行按钮已经为可用的绿色状态。

![but](https://ricebai.github.io/img/posts/android-studio-run/but.jpg)

#### Virtual Device

点击运行，因为首次运行没有配置虚拟机，会进入虚拟机选择界面，我们点击 `Create New Virtual Device` 创建一个新的虚拟机。

![device](https://ricebai.github.io/img/posts/android-studio-run/device.jpg)

#### 模拟手机型号

这里选择支持手机型号的虚拟机，我选择了支持 `Pay Store` 的 `Nexus 5X`，当然你们可以选择其他，点击 `next`。

![device](https://ricebai.github.io/img/posts/android-studio-run/device1.jpg)

#### 虚拟机系统

这里选择对应系统，我选择了 `Android 8.0 Oreo`，点击 `Download`。

![device](https://ricebai.github.io/img/posts/android-studio-run/device2.jpg)

同意协议

![device](https://ricebai.github.io/img/posts/android-studio-run/device3.jpg)

下载并安装，完成后点击 `Finish`。

![device](https://ricebai.github.io/img/posts/android-studio-run/device4.jpg)

#### 完成

选中安装好的虚拟机，点击 `next`，点击 `Finish`。

![device](https://ricebai.github.io/img/posts/android-studio-run/device5.jpg)

#### 问题

如果不幸遇到这种情况，计算机不支持硬件加速虚拟化

![device](https://ricebai.github.io/img/posts/android-studio-run/device7.jpg)

可以尝试重启电脑进入 BIOS，设置 Intel  Virtualization Technology 这个选项为 `Enable` 。

不同型号的电脑进入BIOS方式不同，一般由  `F2`  `F11`  `F12`  `Delete` 等

### 运行成功

虚拟机启动成功，运行 APP。

![device](https://ricebai.github.io/img/posts/android-studio-run/run.jpg)

### 虚拟机管理

再次进入虚拟机管理

![device](https://ricebai.github.io/img/posts/android-studio-run/device8.jpg)

找到安装好的虚拟机，点击运行。

![device](https://ricebai.github.io/img/posts/android-studio-run/device9.jpg)
