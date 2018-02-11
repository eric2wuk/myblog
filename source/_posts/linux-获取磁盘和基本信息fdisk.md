---
title: linux 获取磁盘信息, 添加硬盘, 分区
date: 2018-02-11 20:50:48
categories: [coding]
tags: [Linux,notes,BigDate,env,software, LinuxCommand]
---
* 磁盘分区
* Linux 系统默认所有文件都在/dev 目录下
* sata sas scsi ide 常用接口类型
* fdisk -l 查看系统所有硬盘的分区情况
    * 系统一共有几块硬盘
    * 每个硬盘的分区情况(硬盘空间是否有空余)
<!----more-->
```jshelllanguage
[root@localhost tmp]# fdisk -l

Disk /dev/sda: 53.7 GB, 53687091200 bytes
255 heads, 63 sectors/track, 6527 cylinders
Units = cylinders of 16065 * 512 = 8225280 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk identifier: 0x000ba94c

   Device Boot      Start         End      Blocks   Id  System
/dev/sda1   *           1          64      512000   83  Linux
Partition 1 does not end on cylinder boundary.
/dev/sda2              64        6528    51915776   8e  Linux LVM

Disk /dev/mapper/VolGroup-lv_root: 51.1 GB, 51078234112 bytes
255 heads, 63 sectors/track, 6209 cylinders
Units = cylinders of 16065 * 512 = 8225280 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk identifier: 0x00000000


Disk /dev/mapper/VolGroup-lv_swap: 2080 MB, 2080374784 bytes
255 heads, 63 sectors/track, 252 cylinders
Units = cylinders of 16065 * 512 = 8225280 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk identifier: 0x00000000
```
* /dev/sda --硬盘1 sda1第一个分区 sda2第二个分区 sda3第三个分区
* /dev/sdb --硬盘1 sdb1第一个分区 sdb2第二个分区 sdb3第三个分区
* /dev/sdc --硬盘1 sda1第一个分区 sda2第二个分区 sda3第三个分区
* 为虚拟机添加硬盘
    * 关闭虚拟机, 操作
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-90698082d779918e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-a3a7490a24409e31.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-c172cf18d333ce96.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 使用默认选项
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-63b2dc1a9f886b29.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-0a84fd4299c17aea.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 选择单个文件
    * ![image.png](http://upload-images.jianshu.io/upload_images/4832809-e42bc8b7c2a891c8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * ```jshelllanguage
        [root@localhost ~]# fdisk -l
        
        Disk /dev/sda: 53.7 GB, 53687091200 bytes
        255 heads, 63 sectors/track, 6527 cylinders
        Units = cylinders of 16065 * 512 = 8225280 bytes
        Sector size (logical/physical): 512 bytes / 512 bytes
        I/O size (minimum/optimal): 512 bytes / 512 bytes
        Disk identifier: 0x000ba94c
        
           Device Boot      Start         End      Blocks   Id  System
        /dev/sda1   *           1          64      512000   83  Linux
        Partition 1 does not end on cylinder boundary.
        /dev/sda2              64        6528    51915776   8e  Linux LVM
        
        Disk /dev/sdb: 107.4 GB, 107374182400 bytes
        255 heads, 63 sectors/track, 13054 cylinders
        Units = cylinders of 16065 * 512 = 8225280 bytes
        Sector size (logical/physical): 512 bytes / 512 bytes
        I/O size (minimum/optimal): 512 bytes / 512 bytes
        Disk identifier: 0x00000000
        
        
        Disk /dev/mapper/VolGroup-lv_root: 51.1 GB, 51078234112 bytes
        255 heads, 63 sectors/track, 6209 cylinders
        Units = cylinders of 16065 * 512 = 8225280 bytes
        Sector size (logical/physical): 512 bytes / 512 bytes
        I/O size (minimum/optimal): 512 bytes / 512 bytes
        Disk identifier: 0x00000000
        
        
        Disk /dev/mapper/VolGroup-lv_swap: 2080 MB, 2080374784 bytes
        255 heads, 63 sectors/track, 252 cylinders
        Units = cylinders of 16065 * 512 = 8225280 bytes
        
        ```
* 添加硬盘sdb, 使用前需要接入并分区
    * fdisk /dev/sdb -- 交互界面 引导操作 随时m查看help
    * n -- 添加分区 -- 主分区+拓展分区(逻辑分区) <=4 
    * 步骤
        1. fdisk 设备名称(/dev/sdb)
        2. partx -a /dev/sdb --重新识别系统分区
        3. mkfs.ext4 /dev/sdb --格式化
        4. mount /dev/sdb6 /mnt -- 临时挂载
        ```jshelllanguage
        [root@localhost dev]# df -h
        Filesystem            Size  Used Avail Use% Mounted on
        /dev/mapper/VolGroup-lv_root
                               47G  4.0G   41G   9% /
        tmpfs                 491M   76K  491M   1% /dev/shm
        /dev/sda1             477M   36M  417M   8% /boot
        /dev/sr0              3.7G  3.7G     0 100% /media/CentOS_6.9_Final
        [root@localhost dev]# mount /dev/sdb6 /mnt
        [root@localhost dev]# df -h
        Filesystem            Size  Used Avail Use% Mounted on
        /dev/mapper/VolGroup-lv_root
                               47G  4.0G   41G   9% /
        tmpfs                 491M   76K  491M   1% /dev/shm
        /dev/sda1             477M   36M  417M   8% /boot
        /dev/sr0              3.7G  3.7G     0 100% /media/CentOS_6.9_Final
        /dev/sdb6              25G   44M   24G   1% /mnt

        ```
        5. 永久挂载 写入 /etc/fstab
        5. umount --卸载挂载 
* 文件系统 ext2 ext3 ext4 xfs
* block: linux 操作系统管理文件的最小(逻辑)单位