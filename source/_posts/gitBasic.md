---
title: gitBasic
date: 2018-02-02 17:04:44
tags:
---
1. git 学习
    * 廖雪峰的Git教程 git中文手册、比较适合新手
    * 视频教程：Git零基础实战视频教程（共49课时）
    * git权威指南 比较全面和深入的
1. 分布式git 集中式svn
    - 分布式不用联网,
2. 第一步 涉及到的不熟悉操作
    * mkdir <filename>
    * git init
    * ls
    * ls -ah            //查看隐藏可读文件 -t修改时间倒叙 -l详细信息 --color=auto
    * git commit -m "新添加testme.txt文件commit信息"
    * git add -A          //全部修改 git add . //不包括删除的全部修改
    * git diff           查看工作区修改 git diff <filename> 查看单个文件修改
    * git diff --cached   // 查看 stage 与 分支上 diff
    * git status           //查询当前状态
    * git reset <file>        // 撤销提交单独文件 git reset        // unstage all due changes
    * git reset --hard HEAD^   //可能发生转义, 可改写成 "HEAD^" 或者HEAD^^或者 HEAD~及HEAD~1,n版本回退HEAD~n
    * git reset --hard 32141   //后退到指定前几位32141的版本
    * git log 退出 <q>,
    * git log --graph --pretty=oneline --abbrev-commit      //图表 一行 显示提交信息
    * git reflog
    * vim编辑器 insert esc :x 退出
    * git checkout -- <filename>舍弃工作区某一文件的修改
    * 先修改提交到暂存, 删除提交到暂存, 那么暂存区只有删除, 回退也将回到删除与修改前的
    * ssh-keygen -t rsa -C "youremail@example.com" 自动生成ssh
    * git remote add origin git@oschina:dozesun/learngit.git //为本地仓库添加远程仓库
    * 修改远程仓库命令 git remote set-url origin [url]
    * 删除远程仓库命令 git remote rm origin
    * git push -u origin master //第一次推送master分支的所有内容；
    * git push [默认origin] [current分支], git push orgin master
    * git clone git@oschina:dozesun/learngit.git
    * git checkout -b dev //新建dev分支,并切换dev分支
    * $git branch dev , $git checkout dev
    * sourcetree 未提交修改切换分支, 不丢失git command实现方式 //想多了,本身git就是如此

#### 小结
  * Git鼓励大量使用分支：
    *  查看分支：git branch
    *  创建分支：git branch <name>
    *  切换分支：git checkout <name>
    *  创建+切换分支：git checkout -b <name>
    *  合并某分支到当前分支：git merge <name>
        merge冲突是行操作,
    *  删除分支：git branch -d <name>
    *  git log --graph --pretty=oneline --abbrev-commit
    * git stash, git stash list, git stash pop, git stash apply , git stash drop,
    * git stash apply stash@{0}
    * git branch -d <branchname> , -D 强制删除
