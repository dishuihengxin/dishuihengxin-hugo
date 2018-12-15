---
title: "Git学习系列笔记(1)"
subtitle: "git的简单介绍和安装"
date: 2018-09-19T23:09:38+08:00
categories: "operation"
description: "Git is a version controller and a very handy tool."
keywords: ["git，github,韦世滴的博客"]
tags: ["git","github"]
draft: false
nocomment: true
postmeta: true
notoc: true
seealso: true
bigimg: [{src: "https://res.cloudinary.com/kalid/image/upload/blog/img/banner3.jpg"}]
---

[Git](https://git-scm.com/)是一个免费开源的分布式版本控制系统，旨在快速、高效的处理从小型到大型项目版本管理。最初是因为BitKeeper不再免费提供给Linux社区使用，从而Linux Torvalds用C在一个月内迅速开发出Git给社区对Linux开发代码版本控制器。也是因为Git易于学习、小型便捷和出色的性能，逐渐超越了[Subversion](http://subversion.apache.org/),CVS,ClearCase等SCM工具，可以被使用在任何的操作系统之上，安装也是十分的简单快捷，被越来越多的项目开发者使用，迅速成为最流行、使用最多的分布式版本控制系统。到目前为止，像[GitHub](https://github.com/)、[Bitbucket](https://bitbucket.org/)、[GitLab](https://about.gitlab.com/)等等都是基于Git的基础来实现的。

我相信只要是IT行业者都深知项目版本的管理重要性，所以学习和掌握Git是一件不可言喻的重要。今天就来分享一下自己在学习使用Git的总结，如有理解错误的地方请大家指出，关于Git的知识我会不断的更新和补充，希望对正在学习Git的同学有所帮助。

分布式的优越性不言而喻，有分布式架构，分布式存储，分布式数据库...，这些词我们也会经常的听到，关于版本控制系统的集中式和分布式的对比，可以移步参看[廖雪峰老师的这篇文章](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001374027586935cf69c53637d8458c9aec27dd546a6cd6000),讲的还是蛮不错的。下面就直接切入正题，开始Git的学习之旅。

##### 1.Git的二进制安装
Git的安装很简单，目前大多数Linux系统都已经把Git默认安装，这里给常见系统的快速安装方法：

- Linux系统上安装Git

  - `Debian/Ubuntu:` 
    ```bash
    apt-get install -y git
    ```

  - `Centos/Redhat:`
	```bash
    yum install -y git
    ```

要想了解更多Linux发行版本安装Git的方法，可以参看官方的安装指导文档[http://git-scm.com/download/linux](http://git-scm.com/download/linux)。

- Window系统上安装Git

    可以直接从[https://git-scm.com/download/win](https://git-scm.com/download/win)下载Windows版本的`exe`文件进行安装Git最新版本，自动安装命令和UI界面。

- Mac系统上安装Git

    直接`homebrew`安装或是在[http://git-scm.com/download/mac](http://git-scm.com/download/mac)下载进行安装最新版本。

##### 2.源码安装`Git`的方法

- `Centos/Redhat:`

```bash
$ yum update -y 
$ yum remove git -y
$ yum install -y dh-autoreconf expat-devel gettext-devel perl-devel zlib-devel asciidoc xmlto docbook2X
$ wget https://github.com/git/git/archive/v2.20.0.tar.gz
$ tar xvf v2.20.0.tar.gz
$ cd git-2.20.0/
$ make configure
$ ./configure --prefix=/usr/local/git
$ make && make install prefix=/usr/local/git
$ cp -r /usr/local/git/bin/* /usr/bin/ 
$ git --version
git version 2.20.0 
$ cd ~ && rm -rf git-2.20.0/ v2.20.0.tar.gz
```
- `Debian/Ubuntu:`

```bash
$ apt-get update -y
$ apt-get install -y  build-essential libssl-dev libcurl4-gnutls-dev libexpat1-dev gettext autoconf zlib1g-dev 
$ wget https://github.com/git/git/archive/v2.20.0.tar.gz
$ tar -xf v2.20.0.tar.gz 
$ cd git-2.20.0
$ make configure
$ ./configure --prefix=/usr/local/git
$ make && sudo make install prefix=/usr/local/git
$ cp -r /usr/local/git/bin/* /usr/bin/   
$ git --version
git version 2.20.0
$ cd .. && rm -f git-2.20.0/ v2.20.0.tar.gz
```

更多的安装信息可以参看`Git`官方文档：[https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)。

相关资源：

1. Git官方网址：[https://git-scm.com](https://git-scm.com)
2. Git官方Github：[https://github.com/git/git](https://github.com/git/git)
3. Git官方文档：[https://git-scm.com/doc](https://git-scm.com/doc)
4. 在线Github学习手册(PDF)：[github-git-cheat-sheet.pdf](/books/github-git-cheat-sheet.pdf)
5. 在线Git学习手册(PDF中文版)：[pro-git-book.pdf](/books/pro-git-book.pdf)
6. 推荐一个Git的学习课程：[玩转Git三剑客](/posts/git-learn-course-recommendation/)