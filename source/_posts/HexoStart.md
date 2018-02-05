---
title: Hexo 搭建博客
date: 2018-02-02 14:27:54
categories: [coding]
tags: [hexo]
---
### 折腾博客
#### 前言
* 逻辑很乱没整理, 不要看这篇文章
* 参考 https://www.ezlippi.com/blog/2015/03/github-pages-blog.html
* 如果有网络问题可以考虑自己买一个国外服务器搭一个梯子
#### 操作
* 先确认git ssh连接
![image.png](http://upload-images.jianshu.io/upload_images/4832809-393babc4adff17ee.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
ok 但是好像配置的github账号不对, 去重新设置了下
![image.png](http://upload-images.jianshu.io/upload_images/4832809-2683e76c0b6d52aa.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![image.png](http://upload-images.jianshu.io/upload_images/4832809-fa5f39e7bc098f5c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
ok
失败![image.png](http://upload-images.jianshu.io/upload_images/4832809-afe009978fc4d245.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
原因, 我看看
![image.png](http://upload-images.jianshu.io/upload_images/4832809-bea48c6495044288.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
域名换成了https://ericsun22.github.io/blogs/index
#### Hexo
同事推荐Hexo, 看了看, 好像更简单, 值得尝试
官网 https://hexo.io/zh-cn/docs/writing.html
* 安装node
![image.png](http://upload-images.jianshu.io/upload_images/4832809-63e3b3d26ed04f6b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 国内环境换一个镜像还是有必要的
![image.png](http://upload-images.jianshu.io/upload_images/4832809-8917d55f5e7c0082.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![image.png](http://upload-images.jianshu.io/upload_images/4832809-c3685f6841b9c8f0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* cnpm 看起来不错
![image.png](http://upload-images.jianshu.io/upload_images/4832809-b3425ac2627388ca.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 折腾了以后感觉不错, 那就不在window本地搞了, 去我的服务器 white上玩一下, 建一个git库, 本地操作远程
* 我的服务器, 环境还没配齐 需要安装npm git
* 我有conda 可以用来安装
* conda install -c conda-forge nodejs
![image.png](http://upload-images.jianshu.io/upload_images/4832809-6ade9c139f13cca4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 发现有网络问题?!
* 那先将git放在 gitee上吧Ok
* 启动 hexo server -p 80
![image.png](http://upload-images.jianshu.io/upload_images/4832809-9228af7f9a61754c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 就这样成功