---
layout: post
title: Nginx服务器管理脚本
description: "Linux系统Nginx通过脚本自启动"
category: "Linux"
tags: ["Linux", "Nginx"]
---
##Nginx服务器管理脚本

1. 在/etc/init.d/文件夹中新建脚本文件nginx.sh（服务器重启时，nginx.sh自动运行）

2. 将如下内容复制到nginx.sh文件中

3. chmod 755 nginx.sh

4. 运行sh nginx.sh

5. 管理命令如下：
    启动：nginx start
    重启:nginx restart
    停止：nginx stop
    重载：nginx reload|graceful

{% gist 9894229 %}
