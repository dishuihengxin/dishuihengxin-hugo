---
title: "Keycloak Service Installation Process"
subtitle: "Keycloak Service Installation Process"
date: 2019-10-18T19:17:35+08:00
draft: true
categories: "operation"
description: "kalid.io"
keywords: ["keycloak 安装","单点登录之 keycloak"]
tags: ["keycloak","docker","SSO"]
nocomment: true
postmeta: true
notoc: true
seealso: true
bigimg: [{src: "https://res.cloudinary.com/kalid/image/upload/blog/img/banner3.jpg"}]
---

### keycloak 是什么

[keycloak](https://www.keycloak.org) 是一个开源的[单点登录（SSO）](https://en.wikipedia.org/wiki/Single_sign-on)认证产品，提供针对现代应用程序和服务的开源身份和访问管理的解决方案，几乎不用额外编写多余的代码就可以快速接入应用，帮助我们保护应用程序和服务的认证安全问题。目前由 [Red Hat](https://en.wikipedia.org/wiki/Red_Hat) 领导的 Jboss 社区管理维护。

keycloak 有着很大强大的功能，包括用户注册，社交登陆，单点登录，kerberos 桥接，身份代理，客户端适配器，LDAP、AD域支持，管理控制台，标准协议支持（OAuth 2.0 、 SAML 和 OpenID），权限划分、自定义主题等。

- 单点登录： 应用程序可以直接接入 keycloak 进行身份验证，而不需要应用去处理认证表单和存储用户账户。一键登录后即可以对多应用进行使用。当然了，这同样适用于注销登录操作。

- 社交登录： keycloak 支持各类社交账号登录功能，目前支持有 GitHub、Facebook、Google、Twitter等，还支持 OpenID Connect、SAML、OAuth 2.0 认证方式。我们只需要在管理控制台上选择添加对应的社交网络即可，不需要我们更改应用程序的代码。
![img]()

- LDAP、AD、RDBMS 支持：keycloak 内置支持，可以接入现有的 LDAP、Active Directory 服务和关系型数据库（RDBMS）中已有的用户，实现已有的用户安全认证。
![img]()

- 便捷的管理控制台：keycloak 提供 Web 端的管理控制台界面，管理员可以直接在控制台上集中管理 keycloak 的各项配置，很方便就可以进行创建管理各种应用，包括启用、禁用、联合身份、权限粒度管控、用户、会话等。

- 客户端适配全：keycloak 客户端适配器使保护应用程序和服务的安全变得非常的容易，提供多语言、多平台的适配器，如 Java，Nodejs、Python、Android、iOS等。同时 keycloak 也提供标准的协议支持，openID Connect 库、SAML 库、OAuth 2.0 库均可以快速通过 API 方式接入。

更详细的说明请参看文末提供的 keycloak 相关的文档链接。

### 快速部署 keycloak 服务

我们直接通过 Docker 快速部署一个可用的 keycloak 服务。

>
- OS：Centos 7.6 
- kernel: 3.10.0-1062.1.2.el7.x86_64
- Docker: 19.03.3-ce
- Keycloak: latest

- 快速安装 docker 

```bash
yum install -y yum-utils device-mapper-persistent-data lvm2
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
yum install -y docker-ce docker-ce-cli 
systemctl enable docker.service
systemctl start docker.service
```

- 准备所需的镜像

```bash
images="nginx:stable mysql:8.0 jboss/keycloak:6.0.1"
for i in ${images[@]}; do docker pull $i ;done 
```