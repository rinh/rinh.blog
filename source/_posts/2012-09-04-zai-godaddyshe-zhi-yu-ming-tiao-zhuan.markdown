---
layout: post
title: "在GoDaddy设置域名跳转"
date: 2012-09-04 11:03
comments: true
categories: domain forward godaddy
---

今天要把`rinh.me`这个域名转发到`rinh.github.com`上 , 然后设置了godaddy的forwarding , 发现没动静, 结果发现必须要设置特定的A record才可以. 

过程如下:

* 登录到你的[帐号管理](http://mya.godaddy.com/default.aspx?prog_id=GoDaddy)
* 找到Domains, 点击Launch
* 选择你想制作转发的域名
* 点击Forward, 然后选择Forward Domain
* 选择http或https
* 在Forward to字段里, 输入你想转发到的域名


最重要的一步, 到你的DNS管理中,将你要转发的域名的A记录改为

    @xxx.com  64.202.189.170

[原文链接](http://support.godaddy.com/help/article/422/forwarding-or-masking-your-domain-name)
