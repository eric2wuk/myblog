---
title: shellBasic02
date: 2018-02-15 14:47:24
categories: [Linux]
tags: [Linux,notes,BigDate, LinuxCommand]
---
* \ 代表命令没有结束,写一行继续写
* 第一行 固定声明环境 
    ```jshelllanguage
    #!/bin/bash
    ```

* 脚本注解 \#
    ```jshelllanguage
    #!/bin/bash
    # 测试脚本
      echo "helloworld"
    ```
    <!----more--->
*  脚本权限
    * chmod +x restartwar.sh
* 执行 ,
    * /opt/scripts/restartwar.sh --  直接文件路径执行 
        *  ./restartwar.sh -- 当前目录脚本 , 不能文件名直接执行, 需要路径
    * bash 
    * sh --脚本执行命令
    * source 脚本名称 -- 执行文件
    * . 脚本名称  -- 执行文件
* shell 脚本由上至下, 依次执行
* for 语句
    * 语法1: for 变量 in 值1值2 do done
    ```jshelllanguage
    #!/bin/bash
    # for i in `seq 50` # 反单引号代表预先执行
    for i in {1...50}
    do
    mkdir dir$i
    done
    ``` 
    * 语法2: for((初始;结束条件;步进)) do done
* SUM=$((SUM+i)) -- 两个小括号,或者一个中括号
* 同一行命令需要;隔开
* while [ 条件 ]
    ```jshelllanguage
    #!/bin/bash
    i=1
    while [ i -le 10 ]
    do
    SUM=$((SUM + i))
    i=$[i+1] #let i = i+1
    done
    echo
  
    ```
* read
    ```jshelllanguage
    #!/bin/bash
    while read -r line
    do
    echo `echo $line | awk -F: '{print $1}'`:HELLO # 读取line 以:分割读取第一列后加:HELLO 后打印
    done < /etc/passwd # 将内容传给read
    ``` 
* if
    * 语法1
        ```jshelllanguage
        #!/bin/bash
        if [ 2 -eq 2 ];then # if后有空格, 中括号中间空格
        echo YES
        else
        echo NO
        fi
        ```
* case 语句
    * 语法:
        ```jshelllanguage
        case $变量名称 in
        条件1)
              命令序列
        ;;
        条件2)
        命令序列
        ;;
        条件3)
        命令序列
        ;;
        *)
        echo "useage:$0{top:free|df}"
        ;;
        esac
```        