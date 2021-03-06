---
title: linuxCommand
date: 2018-02-02 17:09:46
categories: [Linux]
tags: [Linux,basic, LinuxCommand]
---
#### 前言
```
买了服务器, 只是折腾的开始, Linux命令其实我也不熟, 用个文档整理下吧 
```
#### 命令
* 这都是基本操作
http://blog.csdn.net/ljianhui/article/details/11100625
    * man # 就是help
    * cd
      ```
      cd /root/Docements # 切换到目录/root/Docements  
      cd ./path          # 切换到当前目录下的path目录中，“.”表示当前目录    
      cd ../path         # 切换到上层目录中的path目录中，“..”表示上一层目录  
      ```
    * ls 这是一个非常有用的查看文件与目录的命令，list之意，它的参数非常多，下面就列出一些我常用的参数吧，如下：
      ```
        -l ：列出长数据串，包含文件的属性与权限数据等  
        -a ：列出全部的文件，连同隐藏文件（开头为.的文件）一起列出来（常用）  
        -d ：仅列出目录本身，而不是列出目录的文件数据  
        -h ：将文件容量以较易读的方式（GB，kB等）列出来  
        -R ：连同子目录的内容一起列出（递归列出），等于该目录下的所有文件都会显示出来  
        # 组合使用
        ls -l  #以长数据串的形式列出当前目录下的数据文件和目录  
        ls -lR #以长数据串的形式列出当前目录下的所有文件  
      ```
    *  find [PATH] [option] [action]  
    *  rm [option] filename… 
        ```
          -f ：就是force的意思，忽略不存在的文件，不会出现警告消息  
          -i ：互动模式，在删除前会询问用户是否操作  
          -r ：递归删除，最常用于目录删除，它是一个非常危险的参数  
        ```
    * cp [选项]... [-T] 源 目的
    * mv [选项] 源文件或目录 目标文件或目录
    * wget [参数] [URL地址]
    * wc 统计一个文件
    * mkdir dirname
    * echo 打印到控制台
    * shutdown 关机操作这个真不常用, 毕竟服务器, -h  关机 参数: [12:00 #定时关机, now 现在关机, 
10 #10分钟关机], -r 重启
    * su 权限的用户变更, 非root 切换需要密码
    * pwd 显示当前目录
    * cat  由第一行开始显示文件内容
    * tac  从最后一行开始显示，可以看出 tac 是 cat 的倒著写！
    * nl   显示的时候，顺道输出行号！
    * more 一页一页的显示文件内容
    * less 与 more 类似，但是比 more 更好的是，他可以往前翻页！
    * head 只看头几行
    * tail 只看尾巴几行
    * df -h 查看磁盘使用
* 复杂的
  - make 将源代码重新编译 http://www.ruanyifeng.com/blog/2015/02/make.html
  - 后台运行任务 http://www.jianshu.com/p/95f10094825b
  - bash
  - 输出重定向 command >out.file  [2>&1] #2>&1表示所有的标准输出和错误输出都将被重定向到一个叫做out.file 的文件中 可省略, 非实时有buffer
  - ps 命令 http://www.cnblogs.com/peida/archive/2012/12/19/2824418.html
  - grep 命令, 相当于命令结果的行搜索 http://www.cnblogs.com/peida/archive/2012/12/17/2821195.html
  - tail 看文件末尾并不断刷新 http://www.cnblogs.com/peida/archive/2012/11/07/2758084.html
  - scp 用来和服务器传文件 http://www.cnblogs.com/no7dw/archive/2012/07/07/2580307.html
  - history 历史操作查看,
  - last 系列, 可以看到登陆了用户的记录, lastb 可以看到一堆世界各地人弱密码失败尝试...
* 终端操作
  -  ctrl +insert 复制
  -  shift+insert 粘贴
 ### 前言
 ```
 1. xshell远程连接时发现, 是不是服务器就无法访问, 感觉不应该啊, 最后发现, 是我这端网络不稳定, 导致xshel的断开连接, 因此程序断开
 2. 让程序在后台跑后，不会占据终端，我们可以用终端做别的事情。
 ```
 ### 方式
 * screen 的方式最好用
    * 安装 yum install screen 
    * screen -R name
 * basic
   - jobs      //查看任务，返回任务编号n和进程号
   * bg  %n   //将编号为n的任务转后台运行
   * fg  %n   //将编号为n的任务转前台运行
   * ctrl+z    //挂起当前任务
   * ctrl+c    //结束当前任务
   * 在Linux中，如果要让进程在后台运行，一般情况下，我们在命令后面加上&即可，实际上，这样是将命令放入到一个作业队列中了：
       $ ./test.sh &
     [1] 17208
   *  在后台运行作业时要当心：需要用户交互的命令不要放在后台执行，因为这样你的机器就会在那里傻等。不过，作业在后台运行一样会将结果输出到屏幕上，干扰你的工作。如果放在后台运行的作业会产生大量的输出，最好使用下面的方法把它的输出重定向到某个文件中：
 command >out.file 2>&1 &
 
 * shell
   ```
   但是如上方到后台执行的进程，其父进程还是当前终端shell的进程，而一旦父进程退出，则会发送hangup信号给所有子进程，子进程收到hangup以后也会退出。如果我们要在退出shell的时候继续运行进程，则需要使用nohup忽略hangup信号，或者setsid将将父进程设为init进程(进程号为1)
   ```
   * nohup   如果让程序始终在后台执行，即使关闭当前的终端也执行（之前的&做不到），这时候需要nohup。该命令可以在你退出帐户/关闭终端之后继续运行相应的进程。关闭中断后，在另一个终端jobs已经无法看到后台跑得程序了，此时利用ps 命令（进程查看命令）
