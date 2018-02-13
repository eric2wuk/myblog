---
title: linux 正则表达式
date: 2018-02-13 22:11:39
categories: [Linux]
tags: [Linux,notes,BigDate, LinuxCommand]
---
### 前言
* 正则这个真的基础
* 主要记一下Linux 中 命令连用 Linux 特有用法
* grep 常用 正则连用
* sed '匹配条件/执行动作'
* awk -F: '{print $1}' /etc/passwd
####
* ^ $ --头尾
* ? * + {m} {m,n} --重复次数 , shell {} 应该需要转义
```jshelllanguage
grep 'n\{3\}' \dirs
```
* . --通配符
* [A-Z] --范围
* grep '^r*n$' /etc/passwd -- 匹配以r开头, n结尾