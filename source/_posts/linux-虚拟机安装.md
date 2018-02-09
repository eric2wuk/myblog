---
title: linux 虚拟机安装
date: 2018-02-09 21:41:46
categories: [coding]
tags: [Linux,notes,BigDate,env]
---
### 步骤
* bios 开启虚拟化选项
* 安装 vm
![image.png](http://upload-images.jianshu.io/upload_images/4832809-66994f5a05a21273.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![image.png](http://upload-images.jianshu.io/upload_images/4832809-3f7f0307f6a8c5bf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* ios 镜像  CentOs 64 6.9 (资料是6.4的, 考虑到一致性, 打算找6.4, 可不好找, 7的话怕有不同,耽误时间)
* Linux 虚拟机操作系统 安装
* 买了一个128G的固态硬盘, 本来是够的, 但没考虑到 我会折腾虚拟机, 考虑到未来不只一个两个虚拟机, 就不再本机上折腾了, 还好带回来了移动硬盘, 那就装在移动硬盘上吧, 也是凄凉, 贫穷使我窘迫
![image.png](http://upload-images.jianshu.io/upload_images/4832809-a31a5e08bce3b4ec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 百度云慢啊, 开个会员吧
* 网易镜像 6g的CentOS 镜像, 先挂着吧
![image.png](http://upload-images.jianshu.io/upload_images/4832809-a810a4541b4b2606.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![image.png](http://upload-images.jianshu.io/upload_images/4832809-12bef4e695cd8b39.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 安装系统
    * 创建虚拟机
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-91fb1c022ca47231.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 典型
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-cd16e11d303d7660.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 稍后安装系统
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-d9f6a1a8205b163c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 起个名字, 我用来学习Hadoop 所以 
    * 建个存储地址
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-b262f12492db5d86.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 这个虚拟机是用来学习Hadoop大数据的所以, 以后环境啊, 软件啊, 还是50G吧
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-c0d2197ee226be49.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 编辑虚拟机
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-b75a50dd1a419f9b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 选择ios1, ios2 为拓展, 暂不需要
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-7a721b37c0105c9f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 安装CentOS
    * 启动虚拟机
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-284f93d35c5db93f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-cc10b979c069de38.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * skip
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-7817a31ece04959b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * discard any data
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-a7fe8dd9435f4e43.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * CentOS 6 connet automatically 设置更改, 这是系统网卡选项, 默认不开启, 需要自己修改
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-c5333569b58fd20d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-74daa773b28f9fc7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 时区 中国上海
    * 账号密码 root 123456 
    * use anyway
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-097870ca7b288dd5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 我是要装桌面系统
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-641c2b6cf2d6cba8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 等吧 15min 左右
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-39d80e515951bbd8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 重启
    * forward 下一步, 下一步
    * 系统时间blabla
    * ok 成功
