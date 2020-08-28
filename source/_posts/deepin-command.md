---
title: deepin-command
date: 2018-02-01 16:23:02
tags: deepin
---

主要介绍了深度操作系统中常用命令、系统命令、通用命令等，您可以通过终端来输入命令来完成相关操作。

<!--more-->
# 基本命令

您可以通过以下命令来查看系统的信息，其他系统相关命令操作可自行搜索查询。

| desc    | command                       |
| ------- | ----------------------------- |
| 查看系统版本  | ` cat /etc/os-version `   |
| 查看内核版本  | ` uname -a `                  |
| 查看软件源信息 | ` cat /etc/apt/sources.list	` |
| 查看命令帮助  | ` man chmod 或 chmod --help`   |

## Apt命令

您可以通过以下命令来查看、安装、卸载、清理、升级等信息。

| desc         | command                                  |
| ------------ | ---------------------------------------- |
| 更新包列表        | ` sudo apt-get update `                  |
| 安装/升级所有可用更新  | ` sudo apt-get dist-upgrade `            |
| 安装应用程序更新     | `  sudo apt-get upgrade	`                |
| dselect安装更新  | `  sudo apt-get dselect-upgrade	`        |
| 查找软件包        | `  apt-cache search packagename `        |
| 显示包相关信息      | `  apt-cache show package `              |
| 显示系统安装统计信息   | `  apt-cache stats`                      |
| 显示包的相关依赖     | `  sudo apt-cache depends package	`      |
| 安装软件         | `  sudo apt-get install package	`        |
| 重装软件         | ` sudo apt-get install package --reinstall	` |
| 强制安装软件       | `  sudo apt-get -f install package	`     |
| 卸载软件         | ` sudo apt-get remove package	`          |
| 卸载软件及配置      | `  sudo apt-get remove package --purge	` |
| 清理旧版本软件缓存    | `  sudo apt-get autoclean	`              |
| 清理所有软件缓存     | `  sudo apt-get clean	`                  |
| 清理不再使用的孤立软件  | `  sudo apt-get autoremove	`             |
| 删除更新和升级的缓存软件 | ` cd /var/cache/apt/archives  & sudo rm *.deb` |

## Deb命令
您可以通过以下命令来查看、安装、卸载、清理、升级等信息。

| desc                                     | command                   |
| ---------------------------------------- | ------------------------- |
| 查看软件包的详细情况。                              | ` sudo dpkg -l	`          |
| 查询已安装的deb包的信息。                           | ` sudo dpkg -s	`          |
| 查看软件包的安装情况。                              | ` sudo dpkg -L package  ` |
| 查看软件属于哪个软件包。                             | ` sudo dpkg -S`           |
| 安装deb包，部分存在depends关系，需要使用`sudo apt-get -f install`来解决。 | ` sudo dpkg -i`           |
| 卸载指定的deb包，不删除软件包的配置文件。                   | ` sudo dpkg -r`           |
| 卸载deb包同时也删除配置文件，部分存在depends关系，需要使用`sudo apt-get remove`来解决。 | ` sudo dpkg -P`           |

## Deepin命令

您可以通过Deepin自定义命令来进行相关操作。

### 启动应用命令

在深度终端界面，输入` deepin-`，按下键盘上`Tab`键，自动显示深度应用系列的列表，部分应用可以直接在终端输入进行启动。

![deepin-](deepin-command/1.png)

> 说明：在中文环境需要查看应用的英文界面时，可直接在终端中输入命令：` LANGUAGE="en_US" deepin-appstore `

在深度终端界面，输入 `dde-`，按下键盘上`Tab`键，自动显示桌面环境的列表。

![dde-](deepin-command/2.png)

> 说明：在中文环境需要查看控制中心的英文界面时（如果不能生效，请先执行`killall dde-control-center`），再可直接在终端中输入命令：` export LANGUAGE="en_US";dde-control-center --show `

### 应用帮助信息

在深度终端界面，输入` deepin-appname -h` 将显示该应用的命令帮助。

![deepin-](deepin-command/3.png)

> 注意：部分深度系列软件不支持-h帮助命令。

### 安装deepin应用

在深度终端界面，您可以直接通过命令匹配并安装应用（含apk/wine/webapps），只需要输入安装命令后再输入deepin./deepin-/dde-/apps.，按下键盘上`Tab`键，自动显示列表。

![deepin-](deepin-command/4.png)

![dde-](deepin-command/5.png)

![deepin.com](deepin-command/6.png)

![apps.](deepin-command/7.png)

### 关机和重启

* 在深度终端界面，还可以直接输入 `sudo init 0 `进行关机。
* 在深度终端界面，还可以直接输入`sudo reboot `进行重启。

### 命令模式和桌面模式

* 在深度桌面环境中，按下键盘上的 `Ctrl + Alt + F2/F3/F4/F5/F6 ` 组合键，进入命令模式。
* 在深度桌面环境中，按下键盘上的`Ctrl + Alt + F1` 组合键，从tty模式恢复桌面模式。

## 通用命令

访问github上面的[linux-command](https://github.com/haloislet/linux-command/releases/tag/v2.0.0)项目，下载appimage安装包，安装成后在启动器界面会有desktop文件，双击运行即可。

![linux-command](https://github.com/haloislet/linux-command/raw/master/mac-screenshot.png)


