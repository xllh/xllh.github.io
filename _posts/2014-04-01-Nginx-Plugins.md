---
layout: post
title: Nginx安装插件
description: "如何给Nginx安装插件"
category: "Linux"
tags: ["Linux", "Nginx", "插件"]
---
##准备
Nginx已经安装，且编译安装。这里以安装[Nginx upload module](http://www.grid.net.ru/nginx/upload.en.html)和[Nginx Upload Progress Module](http://wiki.nginx.org/HttpUploadProgressModule)两个模块为例。

##模块介绍
Nginx upload module上传模块，先将POST提交的内容保存到磁盘，然后将文件信息和POST信息转交给上游服务器，如tomcat。
Nginx Upload Progress Module上传进度模块，上传文件时，向客户端反馈上传进度信息。

##下载并解压
将两个模块最新版本下载到/usr/local/src/文件夹下,并解压到/usr/local/src/文件夹下

##重新编译和安装Nginx

1. ####获取当前Nginx编译指令参数
    /usr/local/nginx/sbin/nginx -V
    获取类似如下编译指令：
    sudo ./configure --with-pcre=/usr/local/src/pcre-8.33 --with-zlib=/usr/local/src/zlib-1.2.8 --with-openssl=/usr/local/src/openssl-1.0.1e –with-http_ssl_module

2. ####重新配置Nginx,保留原来配置参数，加入新插件
    
    进入之前使用的nginx解压包
    
    cd /usr/local/src/nginx
    
    sudo ./configure --add-module=/usr/local/src/nginx_upload_module-2.0.12 --add-module=/usr/local/src/nginx-upload-progress-module-0.8.4 --with-pcre=/usr/local/src/pcre-8.33 --with-zlib=/usr/local/src/zlib-1.2.8 --with-openssl=/usr/local/src/openssl-1.0.1e –with-http_ssl_module
    
    注：根据实际情况，修改两个模块的版本，和之前编译参数配置

3. ####编译
    sudo make
    
    >遇到问题:
	>sudo vim /usr/local/src/nginx/objs/Makefile
    >CFLAGS =  -pipe  -O -W -Wall -Wpointer-arith -Wno-unused-parameter -Werror -g	
    >删除”-Werror”变为
    >CFLAGS =  -pipe  -O -W -Wall -Wpointer-arith -Wno-unused-parameter -g

4. ####安装
    make install
    >我遇到的问题，Nginx版本过高，毕竟两个插件是第三方的。
	
##重启Nginx

    cd /usr/local/nginx/sbin
    sudo ./nginx -s stop
    sudo ./nginx
