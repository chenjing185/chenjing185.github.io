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

![](https://img-blog.csdnimg.cn/2020071712094293.png)

问题原因: nginx的版本高或者服务器版本高的问题

解决方法: 在nginx安装目录下找到src/os/unix/ngx_user.c文件,使用vim打开,将/* cd.current_salt[0] = ~salt[0]:*/这行注释就行了

![](https://img-blog.csdnimg.cn/20200717121206221.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2h1bWFueXI=,size_16,color_FFFFFF,t_70)