---
layout: post
title: 微信公众平台本地开发环境搭建(二)之ngrok
description: "如何在本地测试微信 ngrok"
category: "开发技巧"
tags: ["微信", "ngrok"]
--- 

##1.背景介绍

如[微信公众平台本地开发环境搭建（一）](/2014/04/13/WeiXin-Local-Develop.html)所述方法，比较复杂，需要独立服务器跳转，本地路由器的配置。是否可以让本地电脑作为独立服务器直接使用。

在[GitHub](https://github.com/)上发现一个项目[ngrok](https://github.com/inconshreveable/ngrok),可以将微信请求URL指向本地80端口，大大降低搭建微信开发调试环境的难度。

##2.ngrok简介

[官网](https://ngrok.com/)

[GitHub项目地址](https://github.com/inconshreveable/ngrok)

ngrok

目标：打通到localhost的通道。

两大亮点功能：

1. 将本地HTTP等tcp服务安全地发布到因特网中。安装注册认证后，通过二级域名***.ngrok.com访问本地服务。
2. 可以抓取所有的网络访问细节和重播。启动服务后，通过默认网址http://localhost:4040/http/in，可以查看细节。

##3. 使用方法

1. [官网下载页面](https://ngrok.com/download)，选择对应平台的二进制软件下载，并解压。

2. [官网注册页面](https://ngrok.com/user/login)，注册帐号并登录。

3. 登录后的管理台页面，可以获得：{Your auth token}，用于认证ngrok所安装的计算机。

    将{Your auth token}填入~/.ngrok文件中。格式如下：

    >auth_token: {Your auth token}
    
4. 命令行启动ngrok。
    
    >ngrok -authtoken {Your auth token} 80
    >
    >(如果没有将auth token填入~/.ngrok文件中，则需要指定。且第一次运行ngrok的计算机需要指定。)
    
    或者

    >ngrok 80
    
5. [访问控制台](http://localhost:4040/http/in)。

    ngrok服务的端口为4040，默认监听的端口为80。
    
    访问本地4040端口，可以看到二级域名**http://****.ngrok.com**。
    
    启动本地http应用到80端口。即可在外网通过提供的域名访问到内网http服务。
    
    **提供的二级域名http://****.ngrok.com 每次启动ngrok都是随机生成的，不固定。**
    
6. 配置微信公众平台接口测试帐号的接口配置信息

    URL填写上面获得的临时二级域名即可。
