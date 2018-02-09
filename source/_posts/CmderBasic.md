---
title: CmderBasic
date: 2018-02-02 17:16:40
updated: 2018-02-05 10:58:01
categories: [coding]
tags: [software,tips]
---
#### 前言
为什么要换
* cmd 丑!!!
* 有一些命令还是需要的 ls , grep ssh 
* cmder 有内置一些 vim ssh, 连接服务器用起来更方便

#### 准备工作
* 去官网下载 http://cmder.net/ 
  ![image.png](http://upload-images.jianshu.io/upload_images/4832809-3c3ecd705a016e32.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 启动配置
* 首先是启动配置
  - cmder快捷方式 加到, 我shorts 文件方式文件夹加完之后,Win+r一下输入cmder,即可。当然你也可以采用直接添加环境变量的方式
  - 添加 cmder 到右键菜单: 在某个文件夹中打开终端, 这个是一个(超级)痛点需求, 实际上上一步的把 cmder 加到环境变量就是为此服务的, 在管理员权限的终端输入以下语句即可:
    > Cmder.exe /REGISTER ALL
  之后shift 右键 自然可以看到comder选项
#### 编码
* vim 的时候发现 存在编码问题, 查了这个需要补充下, 总是要被各种软件的编码问题所困扰, 烦
  ![image.png](http://upload-images.jianshu.io/upload_images/4832809-762c702781cfee19.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
#### 快捷键
官方说的快捷键一定要听
![image.png](http://upload-images.jianshu.io/upload_images/4832809-c1e96fbef2bd925b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
#### alias
aliases功能---自定义短命令代替不方便记忆的命令
打开安装目录config/user-aliases.cmd文件，直接修改之。注：看后缀我们知道，修改后的命令只能在cmd下有效，在powershell下无效！
ps: alias 失效, 最后发现是新版控制台可能出了兼容问题, 切换回老版吧![image.png](http://upload-images.jianshu.io/upload_images/4832809-cbbec2a7b0c9e9d5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
#### 修改默认命令提示符号 λ
* 我还觉得这个提示符号挺好看的, 结果它存在问题:当输入 5 个以上字符之后，我们按下 Ctrl + Z 恢复输入时最后会残留一个字符删不掉。
搜了下, 怎样修改 原来参照 http://blog.csdn.net/hicoldcat/article/details/53018216
![image.png](http://upload-images.jianshu.io/upload_images/4832809-e2be5dfc6e35a871.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
#### cmder 分屏
* 开cmder 一般不能是只有一个窗口, 所以分屏自然是需要的
![image.png](http://upload-images.jianshu.io/upload_images/4832809-62d57fc37cf13fa2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
常用的两个, 存在快捷键冲突, 改了下
效果是这样的
![image.png](http://upload-images.jianshu.io/upload_images/4832809-8d0ba69f7b39f9bb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)