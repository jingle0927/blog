---
title: 如何在deepin安装command-not-found提示
date: 2018-02-05 15:51:36
tags: deepin
---

介绍在deepin下终端输入或安装包命令提示未找到命令，执行`apt-cache search xxxx`模糊搜索显示太多包名，不能精确定位到包名，通过安装command-not-found包来进行包名安装详细提示。
<!--more-->


## 安装command-not-found包

可以从[https://www.ubuntuupdates.org/](http://security.ubuntu.com/ubuntu/pool/main/c/command-not-found/)下载最新包。

1. 直接下载command-not-found所需[command-not-found](https://github.com/jingle0927/blog/releases/download/attachment/command-not-found_0.3ubuntu17.10.2_all.deb)、[command-not-found-data](https://github.com/jingle0927/blog/releases/download/attachment/command-not-found-data_0.3ubuntu17.10.2_amd64.deb)、[python3-commandnotfound](https://github.com/jingle0927/blog/releases/download/attachment/python3-commandnotfound_0.3ubuntu17.10.2_all.deb)依赖包（deepin仓库的版本低）。
2. 执行`sudo dpkg -i *command-not-found*.deb`命令安装，或者使用深度软件包安装器批量安装。
3. 下载[command-not-found.mo](https://github.com/jingle0927/blog/releases/download/attachment/command-not-found.mo)配置文件，拷贝到` /usr/share/locale/zh_CN/LC_MESSAGES` 目录下(中文提示)。
4. 安装配置成功后，执行`sudo update-command-not-found`命令更新。


## 查看command-not-found提示

在终端执行任意命令，提示如下。

```
 ~/jingle   master ●  sendmail
The program 'sendmail' can be found in the following packages:
 * exim4-daemon-heavy
 * exim4-daemon-light
 * postfix
 * citadel-server (You will have to enable component called 'universe')
 * courier-mta (You will have to enable component called 'universe')
 * dma (You will have to enable component called 'universe')
 * esmtp-run (You will have to enable component called 'universe')
 * lsb-invalid-mta (You will have to enable component called 'universe')
 * masqmail (You will have to enable component called 'universe')
 * msmtp-mta (You will have to enable component called 'universe')
 * nullmailer (You will have to enable component called 'universe')
 * opensmtpd (You will have to enable component called 'universe')
 * qmail-run (You will have to enable component called 'universe')
 * sendmail-bin (You will have to enable component called 'universe')
 * ssmtp (You will have to enable component called 'universe')
Try: sudo apt install <selected package>

```

```
 ~/jingle   master ●  info
程序“info”尚未安装。 您可以使用以下命令安装：
sudo apt install info

```

```
 ~/jingle   master ●  www
找不到命令'www'，你的意思是：
 Command 'wwt' from package 'wit' (universe)
 Command 'wcw' from package 'winswitch' (universe)
 Command 'dwww' from package 'dwww' (universe)
 Command 'wwl' from package 'wwl' (universe)
www: command not found

```