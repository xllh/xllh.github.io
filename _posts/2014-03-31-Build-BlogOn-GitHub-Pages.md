---
layout: post
title: 在GitHub Pages上搭建博客
description: "如何在GitHub Pages上搭建博客"
category: "工具"
tags: ['GitHub', 'Pages', '建博客', '工具']
---
## 简介

1. [GitHub Pages](http://pages.github.com)只支持静态页面，只需要在GitHub创建一个*特殊项目*，不断向该项目提交静态页面，就可以实现简单的博客功能。
2. 官方推荐使用[Jekyll](http://jekyllrb.com/)在本地编写和调试博客，然后上传博客到GitHub Pages。
3. Jekyll是Ruby语言开发的软件，支持MarkDown,Textile,Liquid模板，有效的组织博客结构和支持镶嵌页面，代码高亮等功能。

## GitHub Pages上创建项目
1. 登录GitHub账户，创建repository，命名为username.github.io(username就是你的GitHub的用户名)
2. 将项目Clone到本地，git clone https://github.com/username/username.github.io
3. 创建首页index.html，输入内容,并将项目提交到GitHub。
4. 等待十分钟左右，访问http://username.github.io。

## 安装Jekyll软件

1. 安装ruby最新版本(版本>1.9)。
2. 安装Jekyll软件，gem install jekyll。
> 更换gem源
>
> 查看源：gem sources
>
> 添加新源：gem sources -a http://ruby.taobao.org/
>
> 删除旧源：gem sources -r http://rubygems.org/

3. 安装支持markdown的rdiscount软件，gem install rdiscount。
4. 运行Jekyll，本地调试博客项目。首先进入本地项目根目录.../username.github.io/,jekyll serve --watch,如果不报错，访问http://127.0.0.1:4000。

## 使用模板和MarkDown编辑管理博客项目

1. 参考https://github.com/xllh/xllh.github.io，将以下除了_posts文件夹外都复制到自己的项目中，进行个性化修改。
2. 各文档内容介绍：
    2.1 _config.yml：全局配置文件，其他内容采用默认配置即可。
    2.2 index.html:默认首页 
    2.3 CNAME：映射到http://username.github.io链接的自己的域名。需要到自己的域名管理中配置cname映射。
    2.4 _layouts:default.html是所有页面的默认父页面，post是所有博客详情页面的父页面。
    2.5 _posts：里面就是自己写的博客文档，md后缀表示采用MarkDown模板，textile后缀表示采用Textile模板。
    2.6 .gitignore:忽略本地_site文件夹，不提交。
    2.7 _site:Jekyll运行时生成的临时目录。
3. 以后只需要在_posts文件夹下写博客，提交就行了。
