---
title: 在deepin下使用Appifier构建Webapp应用
date: 2018-02-11 17:11:31
tags: deepin
---

介绍deepin下如何打包webapp应用，通过图形化appifier打包安装包，自动生成web源文件，然后通过electron-installer-debian打包成deb包格式。

> 当然，还可以打包成[flatpak](https://github.com/endlessm/electron-installer-flatpak)格式。

<!--more-->


## 安装appifier包

1. 从[Appifier github](https://github.com/quanglam2807/appifier/releases)下载deb安装包。
2. `sudo dpkg -i Appifier_x.x.x_amd64.deb`


## 安装npm包

1. 安装npm    `sudo apt-get install npm`
2. 安装electron  `npm install electron --save-dev --save-exact`

## 安装electron-installer-debian包

`npm install -g electron-installer-debian`

## 安装fakeroot依赖包

`sudo apt-get install fakeroot`

## 打包wechat

`electron-installer-debian --src /home/jingle/Desktop/Wechat-linux-x64/ --dest /home/jingle/Desktop/wechat/ --arch amd64`

> 注意：`/home/jingle/Desktop/Wechat-linux-x64/` 目录属于appifier生成目录，生成的时候需要解压deb包`dpkg-deb -R xxx.deb dir` 修改`Exec=/usr/lib/wechat/wechat`（不然启动器没有desktop文件），然后再压缩包`fakeroot dpkg -b dir xxx.deb`。