---
title: 如何在deepin下安装Flatpak包
date: 2018-02-05 12:00:00
tags: flatpak
---

介绍在deepin下安装其他桌面环境的Flatpak包，主要通过[Flathub](https://www.flathub.org/)下载文件，同时还可以去对应的应用官网下载，例如：[Libreoffice](https://zh-cn.libreoffice.org/download/flatpak/)。

<!--more-->

> 在线安装或直接文件安装如果没有runtime运行环境，会自动提示安装runtime环境。

## 链接地址安装

以 https://github.com/openpaperwork/paperwork 项目为例。

1. 获取Flatpak包地址并执行flatpak --user install [paperwork](https://builder.openpaper.work/paperwork_master.flatpakref)命令。
2. 提示安装runtime后，执行`flatpak run work.openpaper.Paperwork`命令。
3. 如果卸载，执行`flatpak --user uninstall work.openpaper.Paperwork` 命令。

```
Installing: work.openpaper.Paperwork/x86_64/master
Required runtime for work.openpaper.Paperwork/x86_64/master (org.gnome.Platform/x86_64/3.26) is not installed, searching...
Found in remote gnome, do you want to install it? [y/n]: y
Installing: org.gnome.Platform/x86_64/3.26 from gnome
[################=   ] Downloading: 174.9 MB/213.0 MB (169.3 kB/s) 


```

## 本地文件安装

1. 下载 [libreoffice.LibreOffice.flatpakref](https://flathub.org/repo/appstream/org.libreoffice.LibreOffice.flatpakref) 文件。
2. 在文件下载目录执行 `flatpak install --user --bundle LibreOffice.flatpak` 命令。
3. 然后运行`flatpak run org.libreoffice.LibreOffice`命令。
4. 如果需要升级，执行`flatpak update --user org.libreoffice.LibreOffice`命令。


>  deepin下已经开始对深度商店上架的deb进行Flatpak替换，保证将来系统和应用更新升级的分离。