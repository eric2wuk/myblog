---
title: PythonEvn
date: 2018-02-02 17:06:51
categories: [coding]
tags: [environment,python ]
---
#### 前言
```
没有图形化界面的Linux, 界面虽然cool, 但是要死的感觉 
```
#### 下载
1. yum install bzip2 # 以前安装过的自然不需要
2. wget https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/Anaconda3-5.0.1-Linux-x86_64.sh        ps: yes, yse, ENTER
3. bash ~/Anaconda3-5.0.1-Linux-x86_64.sh #yes,Enter,yes
4. conda --version #不成功啊?那自己去配下环境变量
    ```
    # 将anaconda的bin目录加入PATH，根据版本不同，也可能是~/anaconda3/bin
    echo 'export PATH="~/anaconda2/bin:$PATH"' >> ~/.bashrc
    # 更新bashrc以立即生效
    source ~/.bashrc
    ```
5. 测试
    ```
    # conda --version
    conda 4.3.30
    # python --version
    Python 3.6.3 :: Anaconda, Inc.
    # python
    Python 3.6.3 |Anaconda, Inc.| (default, Oct 13 2017, 12:02:49) 
    [GCC 7.2.0] on linux
    Type "help", "copyright", "credits" or "license" for more information.
    >>> import numpy
    >>> 
    ```
6. ok, 你既然装成功了, 那你就可以删了
    > rm -rf ~/anaconda3
###  前言
最开始学用的cmder, 但不是长久之计, 所以启用IntelliJ idea (并非是专门的Python开发工具, 我用惯了)作为ide, 配置python

### 步骤
####1 在intelliJ安装python plugin ![image.png](http://upload-images.jianshu.io/upload_images/4832809-070d226cf0815fc3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
####2  新建python项目
![image.png](http://upload-images.jianshu.io/upload_images/4832809-7254ee41ada9977b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
####3 后期使用的时候, 发现需要补一个 Anaconda的环境, 正常来讲很简单
![image.png](http://upload-images.jianshu.io/upload_images/4832809-049efb3d017629b1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![image.png](http://upload-images.jianshu.io/upload_images/4832809-ae987d02049504a6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
####4 但诡异的不成功, 所以我直接改了idea中的依赖文件
![image.png](http://upload-images.jianshu.io/upload_images/4832809-0a088325672279c8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
ps: 检索很慢, 风扇转啊转
* #### 前言
  ```
  有时候我们需要多个不同的Python运行环境, Python2, Python3或者不同包环境
  Conda的环境管理功能允许我们同时安装若干不同版本的Python，并能自由切换。
  ```
* #### 安装conda
  可以通过安装Anaconda来简单的获取conda, Ancaconda是个常用包的集合, 自然包        含了conda, 而我也写了一个教程, linux下的Anaconda安装
http://www.jianshu.com/p/f74b5c79bdad
* #### conda环境的管理
  Conda的环境管理功能允许我们同时安装若干不同版本的Python，并能自由切换。对于上述安装过程，假设我们采用的是Python 3.6对应的Anaconda安装包，那么Python 3.6就是默认的环境（默认名字是root，注意这个root不是超级管理员的意思）。
  ```
  # 创建一个名为python27的环境，指定Python版本是2.7（不用管是2.7.x，conda会为我们自动寻找2.7.x中的最新版本）
  conda create --name python27 python=2.7
  # 小技巧 常用参数 --name 等同于 -n 其他类似
   
  # 安装好后，使用activate激活某个环境
  activate python27 # for Windows
  source activate python27 # for Linux & Mac
  # 激活后，会发现terminal输入的地方多了python27的字样，实际上，此时系统做的事情就是把默认3.6环境从PATH中去除，再把2.7对应的命令加入PATH
 
  # 此时，再次输入
  python --version
  # 可以得到`Python 2.7.14 :: Anaconda, Inc.
  `，即系统已经切换到了2.7的环境
 
  # 如果想返回默认的python 3.6环境，运行
  deactivate python27 # for Windows
  source deactivate python27 # for Linux & Mac
 
  # 删除一个已有的环境
  conda remove --name python27 --all
    ```
* #### 配置下国内镜像还是很有必要的
  如果需要安装很多packages，你会发现conda下载的速度经常很慢，因为Anaconda.org的服务器在国外。所幸的是，清华TUNA镜像源有Anaconda仓库的镜像，我们将其加入conda的配置即可：
  ```
  # 添加Anaconda的TUNA镜像
  conda config --add channels   https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
  # TUNA的help中镜像地址加有引号，需要去掉
  # 设置搜索时显示通道地址
  conda config --set show_channel_urls yes
  ```
#### 
相关文章 http://python.jobbole.com/87522/


### 前言
今天调annacond3 是, 可能是环境出了问题
```bash
[root@myecsid ~]# python
Fatal Python error: Py_Initialize: Unable to get the locale encoding
  File "/usr/lib64/python2.7/encodings/__init__.py", line 123
    raise CodecRegistryError,\
                            ^
SyntaxError: invalid syntax

Current thread 0x00007f2054b04740 (most recent call first):
Aborted
```
### 尝试
重新配了下环境变量 path 清回默认, 为 Anaconda3添加 
#### try01
```bash
#echo 'export PATH="/root/anaconda3/bin:$PATH"' >> ~/.bashrc
#source ~/.bashrc
[root@ ~]# unset PYTHONHOME
[root@ ~]# unset PYTHONPATH
```
python 依旧失败
```bash
[root@ ~]# python
Fatal Python error: Py_Initialize: Unable to get the locale encoding
ModuleNotFoundError: No module named 'encodings'

Current thread 0x00007f62cb4f1740 (most recent call first):
Aborted
```
但conda 启动正常
```bash
[root@myecsid ~]# conda --version
conda 4.3.30
[root@myecsid ~]# conda env list
# conda environments:
#
python27                 /root/anaconda3/envs/python27
root                  *  /root/anaconda3
[root@myecsid ~]# source activate
(root) [root@myecsid ~]# python
Python 3.6.2 |Anaconda custom (64-bit)| (default, Jul 20 2017, 13:51:32)
[GCC 4.4.7 20120313 (Red Hat 4.4.7-1)] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
既然 conda 能正常运行python , 那证明是可以的, 
可能是某些环境变量变更没有生效, 导致多版本冲突
还是重启下服务器
```bash
[root@myecsid ~]# $PATH
-bash: /root/anaconda3/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/root/bin: No such file or directory
[root@myecsid ~]# python
Python 3.6.2 |Anaconda custom (64-bit)| (default, Jul 20 2017, 13:51:32)
[GCC 4.4.7 20120313 (Red Hat 4.4.7-1)] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> quit()
```
果然如此 解决
#### 前言
折腾到了最后发现还是直接安装Anacoda3最好, 环境直接配好, 不冲突, 新电脑, 走遍流程并记录
参考: http://blog.csdn.net/u012318074/article/details/77075209
http://blog.csdn.net/DQ_DM/article/details/47065323
####
* 下载 国内请优先选择清华镜像， 否则速度不保证
* 安装 勾选all users， add Path（这个安装后自己添加也可以）
这里有一个坑， 用管理员模式安装如果path中已配置变量过多，， 可能， path路径配置失败，超过限制最大字节
![image.png](http://upload-images.jianshu.io/upload_images/4832809-35066a8f84bf4ce1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
      慢， 大概10多分钟
![image.png](http://upload-images.jianshu.io/upload_images/4832809-37b94c5f72485a81.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
自带python3环境， 另外创建python2环境
![image.png](http://upload-images.jianshu.io/upload_images/4832809-36285c893f1ee9c2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
