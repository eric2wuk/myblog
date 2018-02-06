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
git push 存在一些问题