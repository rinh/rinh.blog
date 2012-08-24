---
layout: post
title: "一键推送kindle"
date: 2012-08-24 16:01
comments: true
categories: mac applescript kindle
---
自从入手Kindle以来, 就不断折腾中...

Kindle推送的方案真是好, 以至于可以完全脱离开USB数据线, 想看什么书只要推送即可.

想学习如何设置推送可以看[这里](http://www.xiaozhou.net/kindle/register_and_activate_your_kindle-2012-01-12.htm)preview, 当然使用"多看"系统的话更方便.

有了方便的功能, 就会变得更懒, 于是开始琢磨如何在mac上, 一键推送书籍. 

打开Automator, 选择`服务` , `文件或文件夹` , `任何应用程序 `

然后将`Run AppleScript` 拖放进来. 


    on run {input, parameters}
        set theSender to "这里是你的发送邮箱"
        set theRecipient to "这里是kindle的推送邮箱"
        
        tell application "Mail"
            set mymail to make new outgoing message with properties {subject:"mail"}
            tell mymail
                set sender to theSender
                make new to recipient with properties {address:theRecipient}
                tell content
                    repeat with theFileName in input
                        make new attachment with properties {file name:theFileName} at after the last word of the last paragraph
                    end repeat
                end tell
                send
            end tell
        end tell
        
        return input
    end run


保存脚本为`一键推送kindle`

好了, 打开Finder看看吧, 随便选择一个文件, 右键`服务`, 就会找到这个功能. 

* 遇到一个问题就是, 我的系统语言为English, 发送中文名的epub到kindle中就是正常. 如果设置系统语言为简体中文, 则会乱码, 不知道为啥 


