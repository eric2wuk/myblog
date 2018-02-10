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
<!----more--->
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
* mkdir 创建目录 ll 中 第一个字符 d为目录 - 为普通文件
    ```jshelllanguage
    [root@localhost Documents]# ll
    total 4
    drwxr-xr-x. 2 root root 4096 Feb 10 01:53 test
    -rw-r--r--. 1 root root    0 Feb 10 01:42 test.txt
    ```
    * -p 递归创建目录 
    ```jshelllanguage
    [root@localhost Documents]# mkdir -p a/b/c
    [root@localhost Documents]# ll
    total 8
    drwxr-xr-x. 3 root root 4096 Feb 10 01:58 a
    drwxr-xr-x. 2 root root 4096 Feb 10 01:53 test
    -rw-r--r--. 1 root root    0 Feb 10 01:42 test.txt
    ```
* rm 删除文件
    * -f 不提示强制删除
    * -r 删目录及文件
* cp copy 
    * -r 复制目录
    * -a 复制所有(包括文件属性权限,否则继承目标目录默认权限)
* mv 移动或重命名
* Tab 键补齐
* cat 查看文件
* more 分屏查看文件
* head -5 文件名, 查看前5行内容 
* tail 查看文件末尾
    * -n 50 查看50行
    * -f 强制刷新 (查看日志常用)
* ctrl+c 强制关闭
* du 统计文件目录 大小
    * -h 单位换算 更人性化
    * -s 统计容量总和
    * du -sh /root/* 统计目标目录下各个目录分别大小
    ```jshelllanguage
    [root@iz2ze1he9iwe2cr8563ma0z blog]# du -sh /root/*
    5.6G    /root/anaconda3
    126M    /root/blog
    64K     /root/jobs
    46M     /root/learnredis
    12K     /root/learnsh
    109M    /root/lnmp1.4
    136K    /root/lnmp1.4.tar.gz
    124K    /root/lnmp-install.log
    4.0K    /root/myenv
    4.0K    /root/mysql-data-dir-backup20180203170432
    600M    /root/pythonbasic
    20K     /root/test
    ```
* grep --在文件里找符合条件的行
    * -i 不区分大小写
    * -v 取反
    * -A 2 符合条件的钱两行
    * -B 2 符合条件的后两行
    * -n 显示行号
    * -r 递归查询
    * 支持正则表达式
* find 查找文件
    * find 路径 -name "*test*"
    ```jshelllanguage
    [root@iz2ze1he9iwe2cr8563ma0z blog]# find /etc/ -name "ifcfg-eth0"
    /etc/sysconfig/network-scripts/ifcfg-eth0
    ```
    * -type 文件类型 d 文件夹 f 文件
* vi vim (这个内容太多了) http://dozesun.top/2018/02/02/vimbasic/
    * vim 是在vi 上的增强
    * 第一次是在window git 上使用, 解决冲突 直接跳出了vim 直懵逼, 连退出都不会, 哈哈哈
    * 记一下常用的
        * i inset模式 
        * set nu 显示行号
        * dd dd3 删除
        * yy 复制
        * p 粘贴
        * :5 定位行
        * G 快速定位最后一行
        * gg 快速定位第一行
        * u 撤销 
        * :1,$s/nologin/88888888/g  从第一行到最后 将nologin替换为8888888 /g通行替换, 不加/g 只替换每行第一个
        