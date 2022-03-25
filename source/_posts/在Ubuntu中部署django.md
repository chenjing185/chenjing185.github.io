---
title: 在Ubuntu中部署django
date: 2022-03-18 11:38:28
categories:
- python
tags: 
- django
- Ubuntu
- bug
toc: true
readmore: true
sticky: 100
comments: true
---
这是作者本人在Ubuntu中部署django中遇到的一些问题

## 一.Ubuntu中安装nginx报错struct crypt_data’ has no member named ‘current_salt’

![](C:\Users\陈靖\Pictures\Saved%20Pictures\2.png)

问题原因: nginx的版本高或者服务器版本高的问题

解决方法: 在nginx安装目录下找到src/os/unix/ngx_user.c文件,使用vim打开,将/* cd.current_salt[0] = ~salt[0]:*/这行注释就行了
