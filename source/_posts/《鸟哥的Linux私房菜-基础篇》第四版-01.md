---
title: 《鸟哥的Linux私房菜-基础篇》第四版 01
date: 2018-03-06 10:07:43
categories: [Linux]
tags: [Linux,basic, LinuxCommand]
---
《鸟哥的Linux私房菜-基础篇》第四版
#### 前言
* linux 进修一下
#### 笔记
* 0.1 计算机
    * 五大组成单元: 输入, 输出, 计算机cpu 控制单元, 算数逻辑单元, 主存储器
    * cpu 架构大的方面分为 精简指令集: RISC 复杂指令集: CISC 系统
    * 常见的 CISC 指令集 CPU 有 AMD Intel 等 x86 架构的CPU
        * x86 名字来源于 Intel 公司最初研发的 代号 8086 的 CPU , 后来有研发了 80286, 80386 , 因此此架构 CPU 称为 x86 结构
        * Intel 最初的 x86 从8位 升为 16位 32位, 后 AMD 根据此架构 升级修改为 64位, 为区分 64位个人电脑 CPU 架构称为 x86_64
        * CPU 每次能处理的数据量称为字组大小(word_size), 字组大小根据设计分为 32 与 64, 我们称 32位, 64位主要是根据解析的字组而来的
* 0.4 系统层级 kernel , system call , application     
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-8acac1a2486ea37f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * kernel 主要负责, 系统呼叫接口(System call interface), 程序管理(Process control), 内存管理(Memory management), 文件管理系统(Filesystem management), 设备驱动(device drivers)
* 4.2.2 基础命令
    * date 显示系统时间
    * bc 计算器
* 4.2.3 常用快捷键
    * Tab   -- 补齐
    * ctrl + c -- 终止程序
    * ctrl + d -- 结束输入
    * shift + PgUp/PgDn -- 翻页
* 文件系统结构
![image.png](https://upload-images.jianshu.io/upload_images/4832809-73b984ccd2365a89.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
bookmark 5.1 
page 204 / 1051