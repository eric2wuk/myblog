---
title: shellBasic
date: 2018-02-13 21:53:00
categories: [Linux]
tags: [Linux,notes,BigDate, LinuxCommand]
---
#### 前言
* shell 肯定是要会的
* 写个脚本, bla bla
#### 语法
* set 查看环境变量
    * 用户环境变量(/root/.bash_profile)
    * 系统环境变量(/etc/profile)
* 位置变量 --通常和脚本配合使用
    * $0 $1 $2.. $9
    * $0 命令名
    * sh test.sh var1 var2 var3 var4
* 预定义变量
    * $0 保存当前进程或脚本的名称
    * $! 后台运行的最后一个进程的PID好
    * $? 表示程序退出的代表(一般0代表执行成功, 非0代表执行失败)
    * $* 代表所有参数内容(整体)
    * $$ 代表当前进程ID号
    * $# 代表当前shell 的参数个数
    * $@ 代表所有参数内容(逐个读取)
* 自定义变量
    * name=value -- 等号两端不能有空格, 变量对大小写敏感, 没有分号, 尽量使用大写
    * $name -- 取值
* 算数运算
    * $((expression))
    * $[expression] -- [] 等效 两个小括号
    * expr expression -- 符号两侧需要空格
& 内置判断 -- 成功/成立 -- 失败/不成立
    * test 测试表达式
    * [ 测试表达式 ] -- 测试表达式于中括号之间必须有空格
    ```jshelllanguage
    [root@localhost ~]# test $a -lt $b
    [root@localhost ~]# echo $?
    0
    [root@localhost ~]# test $a -gt $b
    [root@localhost ~]# echo $?
    1
    [root@localhost ~]# echo $a $b
    1 2

    ```
    ```jshelllanguage
    [root@localhost ~]# [ $a -lt $b ]
    [root@localhost ~]# echo $?
    0
    [root@localhost ~]# [ $a -gt $b ]
    [root@localhost ~]# echo $?
    1
    ```
* 逻辑符号
    * && 逻辑与 cmd1 && cmd2 -- cmd1命令执行成功, 才执行cmd2
    * || 逻辑或 -- cmd1 || cmd2 -- cmd1命令执行失败, 才执行cmd2
    * ; 无逻辑关系, 只表示执行顺序
* 数值比较
    * -eq -- ==
    * -ne -- !=
    * -gt -- >
    * -ge -- >=
    * -lt -- <
    * -le -- <=
* 字符串比较
    * = -- 两侧有空格
    * !=
    * -z -- 字串长度为伪则为真
    * -n -- 字串长度不伪则为真
    