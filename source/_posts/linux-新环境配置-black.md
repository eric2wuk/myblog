---
title: linux 新环境配置(black)
date: 2018-05-29 18:38:15
categories: [Linux]
tags: [Linux,basic, env]
---
### 前言
* 新开通了一台服务器 腾讯的（阿里快到期了。。续费太贵）
* 想了想，也不用原来 white 的 镜像文件了，重新配置一遍
### 各种
#### python (conda)
* http://dozesun.top/2018/02/02/PythonEvn/
* 极慢 不知道是不是 这回的配置太低了，带宽小
* node 
    * conda install -c conda-forge nodejs
#### 工具
* git
    * yum install git
    * http://dozesun.top/2018/02/02/gitBasic/
* screen
    * http://dozesun.top/2018/02/02/linuxCommand/ 
    * yum install screen
* hexo
    * http://dozesun.top/2018/02/02/HexoStart/
* 域名
    * 迁移 我看了下 域名解析管理 和 服务器是分开的两部分 ， 可以直接 在阿里云服务器上更改
    * 如果有需要的 再 迁移 域名管理到 腾讯云