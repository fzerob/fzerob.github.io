---
layout:     post
title:      Git与Github
subtitle:   学习笔记
date:       2019-08-18
author:     fzerob
header-img: img/gitandgithub/post-bg-gitandgithub.jpg
catalog: true
tags:
    - git
    - github
    - 学习笔记
    - PyCharm
---

> 关于git和githua的学习笔记，入门级别

## 学习资料来源： 
* youtube视频课程，Inty主讲，中文 [《Git和Github入门教学》](https://www.youtube.com/playlist?list=PLRxMjOjh7Y5d_eRLWr-DaujfI2YHgCqIf)

借助于PyCharm (Python) 软件操作，没有git命令行。 讲解很入门，很容易理解。

* blog资料 命令行操作（网上资料太多了）

## 总结笔记

### 第一讲： 什么是git, github
git是工具，用于version control

github网站，云端

### 第二讲 下载安装git
#### 检查是否有git 
Windows: cmd -> git version

> Note: 如果git没有安装在C盘，记得添加环境变量

> 例如: 将D:\Git\Git\mingw64\libexec\git-core 和 D:\Git\Git\bin, 添加到环境变量的path 中，重新打开cmd


### 第三讲 用PyCharm玩GitHub (GitHub to 本地)

1. 新建PyCharm project: 打开PyCharm -> new project -> interpreter 选第二个（python3.7 编辑器）
2. Define Path: Select Preference (Mac)/Setting(Windows) -> Git (under Version control) -> fill “Path to Git” use “…/bin/git” -> select Test -> “ok”
VCS (Version Control System) -> checkout from Version Control -> Git -> URL (from GitHub) -> “Test” -> “Clone” -> “Yes”

>Note: 本地文件夹名字无所谓

### 第四讲 把代码搞到GitHub上 （本地 to GitHub）
1. Make some change in your file （file color change）-> 鼠标右键 Git - Add (告诉git 文件有改变) -> 鼠标右键 Git - Commit file -> 选择上传的内容（一般第二项不用选） （-> 双击会显示出变化）-> write commit message (recommended) -> “commit and push” -> “push” (新版本push 到github上)
2. 可以去github查看：红色删除，绿色新添加。

### 第五讲 把Github上的新代码拉下来 git pull
如果 Github上代码有更新
PyCharm中：
左栏文件夹名称右键 -> Git or VCS -> Git or PyCharm 右上角的小button
Git -> Pull (或在repository中寻找) -> new window : “Pull”

### 第六讲 什么是Git Pull
很简单的一课

### 第七讲 关于branch
master branch: 往往没有权限直接编辑 -> 建立一个新的分支，包括master 分支的所有内容
How to create: GitHub -> Code -> Branch: master -> e.g. tmpBranch
How to clone tmpBranch to local:

1.	Clone or download button

2.	PyCharm: Terminal: git fetch -> failed

3.	VCS -> Git -> fetch

How to change branch local: Git:master-> select tmpBranch -> checkout
所有更新均发生在tmpBranch

### 第八讲 PR = Pull Request, Merge
> 自己的branch拉到master branch中 
##### How 
Github: select tmpBranch -> select new pull request -> new windows
Write commit, select who should read your code
-> create pull request
-> message: This branch has no conflicts with the base branch.

### 第九讲 网站Stackshare
> 用来查看比较那些软件在哪些公司使用，普及情况之类
> 除了github之外以下也是git软件Bitbucket GitLab

 





