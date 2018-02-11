---
title: Linux 压缩和解压工具 jar命令
date: 2018-02-11 20:13:08
categories: [Linux]
tags: [Linux,notes,BigDate, LinuxCommand]
---
* tar --打包命令
    * -z gaip 压缩 tar.gz
    * -g bzip2 压缩 tar.bz2
    * -c --create package
    * -v --show process on console
    * -x --decompression
    * -f --后面 接档名
    * -t --查看
    * 压缩 : tar -zcvf 压缩后的包名.tar.gz 压缩的目标
    * 解压: tar -zxvf 压缩后的包名.tar.gz [-C 目标目录]
    * [root@localhost tmp]# tar -zcvf varlog.ta.gz /var/log/
    * 压缩: tar -jcvf 压缩后的包名.tar.bz2 压缩的目标
    * 解压: tar -jxvf 压缩后的包名.tar.bz2 [-C 目标目录]
    * 查看: tar -ztvf 压缩后的包名.tar.gz -- 查看包含文件
* zip
    * 压缩: zip 压缩目标
    * 解压: unzip 压缩包名
* rar -- Linux 默认不支持    