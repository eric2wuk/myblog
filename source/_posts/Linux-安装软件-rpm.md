---
title: Linux 安装软件 rpm, yum
date: 2018-02-12 11:22:36
categories: [Linux]
tags: [Linux,notes,BigDate, LinuxCommand]
---
* 为虚拟机选择光驱镜像 CentOS
```jshelllanguage
[root@localhost ~]# mount /dev/cdrom /media
mount: block device /dev/sr0 is write-protected, mounting read-only
[root@localhost /]# cd /media/
[root@localhost media]# ll
total 564
-r--r--r--. 2 root root     14 Mar 29  2017 CentOS_BuildTag
dr-xr-xr-x. 3 root root   2048 Mar 29  2017 EFI
-r--r--r--. 2 root root    212 Nov 27  2013 EULA
-r--r--r--. 2 root root  18009 Nov 27  2013 GPL
dr-xr-xr-x. 3 root root   2048 Mar 29  2017 images
dr-xr-xr-x. 2 root root   2048 Mar 29  2017 isolinux
dr-xr-xr-x. 2 root root 534528 Mar 29  2017 Packages
-r--r--r--. 2 root root   1359 Mar 28  2017 RELEASE-NOTES-en-US.html
dr-xr-xr-x. 2 root root   4096 Mar 29  2017 repodata
-r--r--r--. 2 root root   1706 Nov 27  2013 RPM-GPG-KEY-CentOS-6
-r--r--r--. 2 root root   1730 Nov 27  2013 RPM-GPG-KEY-CentOS-Debug-6
-r--r--r--. 2 root root   1730 Nov 27  2013 RPM-GPG-KEY-CentOS-Security-6
-r--r--r--. 2 root root   1734 Nov 27  2013 RPM-GPG-KEY-CentOS-Testing-6
-r--r--r--. 1 root root   3380 Mar 29  2017 TRANS.TBL
[root@localhost media]# ^C
```
* 查看 Packages/
```jshelllanguage
[root@localhost media]# cd Packages/
[root@localhost Packages]# ll | wc -l
3242
```
<!----more--->
* .rmp --使用
    * -qa 查询已安装的rpm包
    * -ivh packageName --安装
    ```jshelllanguage
        * [root@localhost Packages]# rpm -qa |grep zlib
          zlib-1.2.3-29.el6.x86_64
          [root@localhost Packages]# rpm -ivh zlib-devel-1.2.3-29.el6.x86_64.rpm 
          warning: zlib-devel-1.2.3-29.el6.x86_64.rpm: Header V3 RSA/SHA1 Signature, key ID c105b9de: NOKEY
          Preparing...                ########################################### [100%]
             1:zlib-devel             ########################################### [100%]
          [root@localhost Packages]# rpm -qa |grep zlib
    ```

    * -e packageName --卸载
    * -qf fileName --查看某文件属于哪个安装包
    ```jshelllanguage
    [root@localhost /]# rpm -qf /etc/yum.repos.d
    yum-3.2.29-81.el6.centos.noarch
    
    ```
* yum命令 -- 用来管理rpm
    * yum list --列出可用的 仓库上有@符号 已安装
     ```jshelllanguage
    [root@localhost /]# yum list | grep httpd-tools
    httpd-tools.x86_64                         2.2.15-59.el6.centos          @anaconda-CentOS-201703281317.x86_64/6.9
    httpd-tools.x86_64                         2.2.15-60.el6.centos.6        updates
    ```
    * yum -y install httpd-devel.x86_64  -- 安装 先解析依赖, 同时安装依赖包
        * -y 提示直接y确认
    * yum -y remove httpd-devel.x86_64  --卸载
    * 配置yum仓库
        * 常用 mirrors.163.com mirrors.sohu.com
        * 仓库配置文件路径 /etc/yum.repos.d
        * DNS解析
        
    