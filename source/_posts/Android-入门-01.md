---
title: Android 入门 01
date: 2018-07-06 11:07:47
categories: [coding,Android] 
tags: [Android]
---
### 前言
* 对Android 来一些简单的了解 整理下笔记
* 摘自 http://www.runoob.com/android/android-architecture.html
### 历史版本
![image.png](https://upload-images.jianshu.io/upload_images/4832809-5d461968aca73433.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 平台版本	API 等级	VERSION_CODE	
* Android 5.1	22	LOLLIPOP_MR1	
* Android 5.0	21	LOLLIPOP	
* Android 4.4W	20	KITKAT_WATCH	KitKat for Wearables Only
* Android 4.4	19	KITKAT	
* Android 4.3	18	JELLY_BEAN_MR2	
* Android 4.2, 4.2.2	17	JELLY_BEAN_MR1	
* Android 4.1, 4.1.1	16	JELLY_BEAN	
* Android 4.0.3, 4.0.4	15	ICE_CREAM_SANDWICH_MR1	
* Android 4.0, 4.0.1, 4.0.2	14	ICE_CREAM_SANDWICH	
* Android 3.2	13	HONEYCOMB_MR2	
* Android 3.1.x	12	HONEYCOMB_MR1	
* Android 3.0.x	11	HONEYCOMB	
* Android 2.3.4
* Android 2.3.3 10	GINGERBREAD_MR1	
* Android 2.3.2
* Android 2.3.1
* Android 2.3 9	GINGERBREAD	
* Android 2.2.x	8	FROYO
* Android 2.1.x	7	ECLAIR_MR1	
* Android 2.0.1	6	ECLAIR_0_1	
* Android 2.0	5	ECLAIR	
* Android 1.6	4	DONUT	
* Android 1.5	3	CUPCAKE	
* Android 1.1	2	BASE_1_1	
* Android 1.0	1	BASE	
### 框架
* Android 操作系统是一个软件组件的栈，在架构图中它大致可以分为五个部分和四个主要层
<!--------------------------------------more----------------------------------->
![image.png](https://upload-images.jianshu.io/upload_images/4832809-73031c0816c80b49.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* Linux 内核
    * 基于 Linux 3.6 包含基础的系统功能，进程管理，内存管理， 设备管理（摄像头，键盘，显示器）同时，内核处理所有 Linux 所擅长的工作，如网络和大量的设备驱动，从而避免兼容大量外围硬件接口带来的不便
* 程序库
    * 在 Linux 内核层的上面是一系列程序库的集合，包括开源的 Web 浏览器引擎 Webkit ，知名的 libc 库，用于仓库存储和应用数据共享的 SQLite 数据库，用于播放、录制音视频的库，用于网络安全的 SSL 库等。
* Android 程序库
    