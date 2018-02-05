---
title: AndroidConnectBot
date: 2018-02-02 17:15:54
tags: [software]
---
#### 前言
* 当需要连接自己的服务器的时候, 身边不一定有电脑, 但手机估计是一定有的,
* 搜了下前人已经把一切都铺好了, 基本对我来讲也就是记录一下ConnectBot软件操作指南了
* 阿里云app本身 有一个ssh组件, 用起来也还行, 本身是阿里云的服务器用它就可以
#### 工具
* ConnectBot: 是一个Android操作系统上的开源Secure Shell客户端。它可以让用户安全地远程连接到运行着SSH守护程序的服务器中。用户可以从Andr​​oid设备输入命令，并在远程服务器上执行，而不是本地Android设备。SSH2的标准加密可以使任何命令和数据在传送中不被窃听。

#### 操作
* 打开后添加![image.png](http://upload-images.jianshu.io/upload_images/4832809-6bc262c9ab96dc7e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 就这样![image.png](http://upload-images.jianshu.io/upload_images/4832809-8e0a9a0477bb6f21.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
#### ssh
当然了, 用密码登陆还是有安全问题万一被碰撞了呢的, 建议使用 ssh登陆, 而且 ConnectBot的公钥操作也很是友好
1. 主页面
2. 管理公钥
3. 添加 
4. 填入信息也可不填, (强烈建议填个信息, 否则时间长了 你都会放了, 这ssh哪来的, 打印登陆也是蒙蔽)
5. 随机算法(点啊点, 有意思)
6. 长按, 把公钥复制了, 登录后 添加到.ssh/authorized_keys, 
7.  OK , 下次连接, ConnectBot 自动会调用私钥连接
#### tips
* 输入的时候, 手机键盘是缺了一些键 比如Tab!!!! 
搜了下,http://www.arbi.se/using-tab-page-updown-and-scrolling-in-connectbot/
 ![image.png](http://upload-images.jianshu.io/upload_images/4832809-107e99d46a0d161d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 就是点一下屏幕, 就出来一个操作栏, ctrl, 上下键, tab 你想要的都有
