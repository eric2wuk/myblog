---
title: EcsConfig
date: 2018-02-02 17:08:06
tags:
---
#### 前言

```
感觉还是需要个云服务器的, 没什么正事, 就是折腾下, 暂时打算用来挂一些, 
小脚本, 例如wx防撤回自动回复, xyy刷听歌量, 云盘, 搭一个自己的梯子也不错.
最开始打算用亚马逊AWS的免费一年服务器, 可发现需要美国信用卡, 
卡着过不去, 搜了下国内发现阿里云也不错, 有免费半年的活动
所以折腾下, 并记录
```
####流程
1. 这是一切的起源
![image.png](http://upload-images.jianshu.io/upload_images/4832809-3857a485fe3793dd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
2. 付账时发现, 那就定个提醒, 明天10:00再说
![image.png](http://upload-images.jianshu.io/upload_images/4832809-beca4cad3d12ec22.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

1. 登陆是以手机阿里云为核心的, 去下载 认证吧, 然后回来继续
![image.png](http://upload-images.jianshu.io/upload_images/4832809-c19f183edf77ad3c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
4. 到点下单, 抢到没什么问题, 我一犹豫买了9.9的那个套餐, 多了40Goss, 还有负载均衡, 感觉很值
5. 买到了自然就去开通了
![image.png](http://upload-images.jianshu.io/upload_images/4832809-0abb7bbac1f73018.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
6. 配置
    * 区域随便选, 我选华北2, 毕竟以前打游戏都选这有感情
        ![image.png](http://upload-images.jianshu.io/upload_images/4832809-7ade8d34aeefd9ac.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 网络, 端口默认没开80, 我可能需要,勾了一下
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-dd8d621a9debc673.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    *  配置不可调, 毕竟免费套餐有点低, 以后真有需求再加
![image.png](http://upload-images.jianshu.io/upload_images/4832809-274d88365aff4367.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 镜像 毕竟是用来搞事情的 Linux 必选
![image.png](http://upload-images.jianshu.io/upload_images/4832809-299b5399a2ad6308.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 密码用了ssh
![image.png](http://upload-images.jianshu.io/upload_images/4832809-8b57a47d9dd4c3f9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  * 搞定开通
![image.png](http://upload-images.jianshu.io/upload_images/4832809-a112d60b0a7c3a37.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 我有了一个云服务器, 开心
![image.png](http://upload-images.jianshu.io/upload_images/4832809-e4303499aa0c08e4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* ### 前言
    * #### 先写了个hello world web响应 
      ps: serve, 我打成了server半天没找到错哪, 恶心
  ![image.png](http://upload-images.jianshu.io/upload_images/4832809-3a702e35a372f98c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
      结果看着ip 很尴尬
    * #### 发给朋友, 微信也不给面子
      ![image.png](http://upload-images.jianshu.io/upload_images/4832809-f031a091b0002a8b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* ### 域名解析还是要配的, 买了个便宜的.top域名, 自用
![image.png](http://upload-images.jianshu.io/upload_images/4832809-5efab33ff4d034f4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![image.png](http://upload-images.jianshu.io/upload_images/4832809-f0fa06b58573709e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* ### 有一些免费域名的网站, 有兴趣的也可以去看看
https://my.freenom.com/clientarea.php
* ### 等待起效
  * 等的时候可以 ping 一下, 看看解析ip, 就可以确认了
* ### 备案
  * 迟迟不起作用, 最后发现还要备案
      ![image.png](http://upload-images.jianshu.io/upload_images/4832809-b030b7025a9fca83.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  * 阿里的服务器, 备案还是挺简单, 填填单, 上传下资料, 身份证啊, 手持身份证啊, 密码啊, 就是这种过程中所清楚告诉你被管控的感觉, 不舒服
  * 王小波同学有话说
![微信图片_20171219202520.jpg](http://upload-images.jianshu.io/upload_images/4832809-a59c3b5ab19c8fc1.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
  * ok, 等通知
![image.png](http://upload-images.jianshu.io/upload_images/4832809-5222d461809f573c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### End
我不清楚什么原因, 我备案慢的出奇, 大概一个月后, 我在忙碌的工作中, 收到了阿里的邮件
补偿了一个月
就这样, 我的个人站正常解析正常了
![image.png](http://upload-images.jianshu.io/upload_images/4832809-ae3598871448f093.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)





