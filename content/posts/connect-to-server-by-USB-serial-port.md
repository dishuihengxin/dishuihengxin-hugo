---
title: "使用 USB Serial Port连接树莓派系统"
subtitle: "Connect to Server by USB Serial Port"
date: 2018-08-14T11:48:03+08:00
draft: false
categories: "operation"
description: "USB serial port是一个很好的方式，在紧急情况下是可以很好的利用这个方法进行系统扑救的。"
keywords: ["kalid,kalid.io"]
tags: ["serial","os"]
nocomment: true
postmeta: true
notoc: true
seealso: true
bigimg: [{src: "https://res.cloudinary.com/kalid/image/upload/blog/img/banner3.jpg"}]
---

树莓派开发的硬件上连接的WiFi有问题时，导致不能通过正常的SSH方式连接进去，在实际操作过程中就遇到这个问题，针对这我们可以采用UBS串口直连的方式进入系统。

1. 找到USB serial串口的端口：设备管理器-->串口(COM和LPT)-->USB serial Port

![](https://res.cloudinary.com/kalid/image/upload/blog/img/win-manager.png)

![](https://res.cloudinary.com/kalid/image/upload/blog/img/win-com-port.png)
2. 根据找到的USB串口，使用PUTTY serial模式来连接终端
![](https://res.cloudinary.com/kalid/image/upload/blog/img/putty-serial-set.png)
3. 进入后在putty上需要敲一下“回车键”切换至debug界面，通过`help`获取command帮助：
![](https://res.cloudinary.com/kalid/image/upload/blog/img/serial-help.png)

4. 输入`console`切换到登陆模式，此时输入账户密码就可以正常登入服务器了。

