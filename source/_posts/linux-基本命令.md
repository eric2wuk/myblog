---
title: linux 基本命令
date: 2018-02-10 00:35:22
categories: [coding]
tags: [Linux,notes,BigDate,env,software]
---
#### 前言
* 我觉得, 我应该跳一下进度了
* 有点太初级了
#### 连接操作
* ifconfig = ip a
    * 查看ip , 内网ip 之类
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-5a6b284b511c878c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 
* ssh username@ipaddress 连接
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-52dc111d3d688968.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* clear 清屏
#### 目录操作
* 目录结构为单根倒置树结构, / 为根目录, 以/ 分割
* 绝对路径 / 相对路径 ./
* 文件及目录 严格大小写
* pwd 打印当前目录
* cd 目录跳转
* ls 列出当前目录文件(包括目录)
    * -l 行打印
    * -d 查看目录本身
    * -a 查看所有文件(以.开头的隐藏文件)
* ll = ls -l 行打印当前目录文件(包括目录), 权限 创建者 创建时间 大小 blabla
* man 命令 查看命令参数
* touch 创建文件 (不常用, 多使用vim, vi 创建并编辑)