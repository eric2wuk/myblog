---
title: 搭建DNS服务器
date: 2018-03-23 19:15:01
tags:
---
#### 前言
* 开发时拿到的开发包, 有时是正式域名或者是测试域名, 调试不便, 搭建DNS服务器, 方便调试
#### 
* 参考 https://www.moerats.com/archives/329/
##### 尝试 Dnsmasq
* 服务器安装 
    * yum install dnsmasq -y 
    * service dnsmasq start
    ![image.png](https://upload-images.jianshu.io/upload_images/4832809-90aad004027204d0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 更改本机 DNS  
  ![image.png](https://upload-images.jianshu.io/upload_images/4832809-c9d5df4ae74aa49d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 折腾好久没成功, 一语惊醒,  ECS 端口是要控制台开放的
![image.png](https://upload-images.jianshu.io/upload_images/4832809-8858b35492b1dbbd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![image.png](https://upload-images.jianshu.io/upload_images/4832809-1c412098323a17b9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
