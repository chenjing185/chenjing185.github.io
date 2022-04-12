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
sticky: 0
comments: true
---

这是作者本人在Ubuntu中部署django中遇到的一些问题

<!-- more -->

**在Ubuntu中部署django本人是参考的django中文网的**
[Ubuntu部署Django项目方法详解](https://www.django.cn/article/show-22.html)

在部署过程中本人遇到了以下问题,特此记录一下:

## Ubuntu中安装nginx报错

### ‘struct crypt_data’ has no member named ‘current_salt’
本人在按照上面的部署教程部署到第八步安装nginx并配置中的sudo make报错

![](https://img-blog.csdnimg.cn/2020071712094293.png)

问题原因: nginx的版本高或者服务器版本高的问题

解决方法: 在nginx安装目录下找到src/os/unix/ngx_user.c文件,使用vim打开,将cd.current_salt[0] = ~salt[0]:这行注释就行了

![](https://img-blog.csdnimg.cn/20200717121206221.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2h1bWFueXI=,size_16,color_FFFFFF,t_70)

在执行完上面的操作后,又出现了新的报错
### make[1]: *** [objs/src/core/ngx_murmurhash.o] Error 1

问题原因: Werror它要求GCC将所有的警告当成错误进行处理 所有导致错误输出 并不能进行下一步

解决方法: 使用vim打开/nginx-1.10.3/objs/Makefile找到 -Werror并去掉在重新make即可
