---
title: "Connect to Server by USB Serial Port"
date: 2018-09-14T11:48:03+08:00
draft: false
nocomment: true
postmeta: false
notoc: true
seealso: false
---


树莓派开发的硬件上连接的WiFi有问题时，导致不能通过正常的SSH方式连接进去，在实际操作过程中就遇到这个问题，针对这我们可以采用UBS串口直连的方式进入系统。

1. 找到USB serial串口的端口：设备管理器-->串口(COM和LPT)-->USB serial Port

![](/img/win-manager.png)

![](/img/win-com-port.png)
2. 根据找到的USB串口，使用PUTTY serial模式来连接终端
![](/img/putty-serial-set.png)
3. 进入后在putty上需要敲一下“回车键”切换至debug界面，通过`help`获取command帮助：
![](/img/serial-help.png)

4. 输入`console`切换到登陆模式，此时输入账户密码就可以正常登入服务器了。

