---
layout: post
title: "在Centos上安装git"
date: 2012-08-16 11:00
comments: true
categories: 操作系统
---

首先,需要确认Centos版本

    cat /etc/issue

然后安装RHEL与EPEL的yum源 [参考](http://www.rackspace.com/knowledge_center/article/installing-rhel-epel-repo-on-centos-5x-or-6x)

centos 5.x

    $ wget http://dl.fedoraproject.org/pub/epel/5/i386/epel-release-5-4.noarch.rpm
    $ wget http://rpms.famillecollet.com/enterprise/remi-release-5.rpm
    $ sudo rpm -Uvh remi-release-5*.rpm epel-release-5*.rpm

centos 6.x

    $ wget http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-7.noarch.rpm
    $ wget http://rpms.famillecollet.com/enterprise/remi-release-6.rpm
    $ sudo rpm -Uvh remi-release-6*.rpm epel-release-6*.rpm

然后就可以使用啦

    yum install git