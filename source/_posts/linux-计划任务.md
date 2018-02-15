---
title: linux 计划任务
date: 2018-02-15 17:00:43
categories: [Linux]
tags: [Linux,notes,BigDate, LinuxCommand]
---
### 一次性任务
* at 4:17 #制定
    * -l 列表
    * -d 删除
    * c+d 退出
### 重复性任务
* crontab
    * 确保服务启动
        * service crond status
        * chkconfig --list | grep crond
    * crontab -e --制定计划任务内容
        * 第一行 书写 crontab time 时间格式
            * 分小时日月周命令 -- 不写用星号填写
                ```jshelllanguage
                0 2 * * 3 cp /etc/passwd /tmp # 每周三凌晨2点备份
                5 1 10,25 * * rm -rf /tmp/*  # 每月10,25号凌晨1点五分执行
                */10 * * * * * # 每10分钟执行一次
                0 1-6 * * * * # 每天凌晨1点到6点整点执行
                ```
    * 重启crond服务
        * service crond restart  