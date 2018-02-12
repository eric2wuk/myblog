---
title: 虚拟机联网 NAT方式注意事项
date: 2018-02-10 11:57:09
categories: [Linux]
tags: [Linux,notes,BigDate,env,software]
---
#### 虚拟机联网注意事项:
* 虚拟机统一以NAT方式连接
<!----more--->
* 当虚拟机联网失败排查
    * 确定VMnet8 网卡的ip地址, ivpV4
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-7729fa4250020c4c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 检查服务 启动
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-b4d0fa7502b34d24.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 检查虚拟机设置 勾选
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-024a6a94fdd1b0b2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 检查NAT相关设置(网关)
* 重启网卡
    * service network restart
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-798912755a598691.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

 * 设置静态IP 
    * 参考 http://blog.csdn.net/exbob/article/details/6410283