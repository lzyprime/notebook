---
title: linux引导卡死
date: 2018-08-20 19:53:30
tags: [Linux,笔记]
categories: 
  - 笔记
  - Linux
---

# linux 引导盘启动不了，卡在引导进不去

<!--more-->

## 解决方案 ：
在出现  **grub**  引导时 按 e 进入编辑界面。在 linux xxxxxxxxx splash quiet --- 一大行后边加两句参数

```bash
acpi_osi=! acpi_osi="Windows 2009"
```

然后 **F10** 引导

每次开机都得输，不想这么麻烦就去改 **/boot/grub/grub.cfg** 文件 在里边找到同样的位置加上
（其实应该去改 **/etc/default/grub** 这样grub更新时会默认加上这两句参数 ： 在 **/etc/defaut/grub** 里加入一行
`GRUB_CMDLINE_LINUX="acpi_osi=! \"acpi_osi=Windows 2009\""` ，然后 `sudo update-grub`）

### 可以安装独立显卡（NVIDIA）的最新闭源驱动，可能会解决问题，不用加这两句，禁用acpi了。  如果可以，就删掉这两句配置
