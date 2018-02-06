---
title: git同时提交两个仓库
date: 2018-02-06 16:51:19
tags: [git,basic]
categories: [coding]
---
###前言
* 到了年尾,整理下自己的git项目,发现存放地很乱,有的放在Github, 有的在码云Gitee, 打算公开的项目, 同时存放于两个库, private项目存放于Gitee
* 参考 http://feitianbenyue.iteye.com/blog/2376791

### 方式
#### 添加remote
* git remote
* git add github git@github.com:eric2wuk/myblog.git
* git pull -u github master
* 不小心和另一个项目弄混了, 一塌糊涂, 只能 git reset, git push -f, 小心翼翼
####  git remote set-url --add 
* 第一种方式命令多了一步, 麻烦一些
* 而第二种则好得多
* git remote set-url --add 添加多个push地址
 ![image.png](http://upload-images.jianshu.io/upload_images/4832809-c681b43019d1a69e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 测试一下
![image.png](http://upload-images.jianshu.io/upload_images/4832809-5e076bd192fe8204.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![image.png](http://upload-images.jianshu.io/upload_images/4832809-acfe290f535fd5d4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
并不成功
* 好像应该是gitee刚刚缓存?, 又试了一下, 结果成功了,done