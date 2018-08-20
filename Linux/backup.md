---
title: linux安装和配置
tags: [笔记,Linux]
categories:
   - 笔记
   - Linux
---

# linux 系统安装

<!--more-->

## 1.引导盘不成功的解决方法

开机grub引导界面，按 e 进入配置，在 splash quiet --- 后边加上两句：  
acpi_osi=! acpi_osi="Windows 2009"  

安装完成后，在/etc/grub中加入默认参数：`GRUB_CMDLINE_LINUX="acpi_osi=! \"acpi_osi=Windows 2009\""`，或直接在 /boot/grub.grub.cfg 文件中相应位置加参数，免每次开机都要加  

**PS :** 安装最新的独立显卡驱动，可能会解决问题，不用加参

## 2.软件

> 切换源： /etc/apt/source.list ,  或者用 “软件和更新”、kde“发现者”等图形化修改。

```bash
sudo apt update && sudo apt upgrade
sudo apt install gcc g++ gdb vim git
```

#### 常用软件

- [vscode](https://code.visualstudio.com/docs/?dv=linux64_deb)
- [gitkraken](https://www.gitkraken.com/download/linux-deb)
- [chrome](https://www.google.com/chrome/thank-you.html?statcb=0&installdataindex=empty)
- [chrome 同步助手](http://www.long-int.com/chrome-helper/)
- [opera](https://www.opera.com/zh-cn/computer/thanks?partner=www&par=id%3D43916%26amp;location%3D421&gaprod=opera)
- [virtualbox](https://www.virtualbox.org/wiki/Linux_Downloads)
- [lantern](https://raw.githubusercontent.com/getlantern/lantern-binaries/master/lantern-installer-64-bit.deb)
- [sougou](https://pinyin.sogou.com/linux/?r=pinyin) ppa:fcitx-team/nightly
- [java download](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
- [Typora](https://www.typora.io/#linux) //markdown editor

```bash
deb 包安装

dpkg -i  {name}.deb
sudo apt install -f -y //如果报错，解决错误
```

## 3.配置文件

- [hosts](configs/hosts) //解决 github ， google 等访问速度问题。`echo hosts >> /etc/hosts`  也没什么用，翻墙
- [vimrc](configs/vimrc) // `cp vimrc ~/.vimrc`
- [i3-config](configs/i3-config) // `cp i3-config  ~/.config/i3/config`
- [vscode](../vscode/vscode.md)

#### 时区同步 utc --> cst   //处理 windows 与 linux 双系统 时间差问题

`timedatectl set-local-rtc 1 --adjust-system-clock`

## 4. 美化

### [www.opendesktop.org](www.opendesktop.org) 

##### gnome-look , kde-store 的总站，想要的icons主题，themes , gnome-shell , kde 部件 , plymouth 开机画面，grub 引导 ，sddm , lightdm ,gdm ……………… 应有尽有

### [美化教程](beautify)

#### 美化只是消遣，有功夫学点有用的，别折腾美化，常换发行版之类的，时间都浪费了
