---
title: useful-linux-commands
date: 2020-09-26 01:26:50
tags: 
    - linux
categories:
    - linux
---
记录工作中常用的linux 命令。
<!-- more -->

## 程序运行过程中查看log


<!-- more -->
```bash
source *.sh  2>&1 | grep "msg"

# save log file
source *.sh 2>&1 | tee log.txt
```



## 添加超链接

```bash
sudo ln -s target /usr/local/bin
```

## 解压 tar.gz 文件

```bash
tar zxvf *.tar.gz
```

## linux 时间戳到人类可读时间的转换

```bash
date -d @1598237685.896981477737427

2020年 08月 24日 星期一 10:54:45 CST
```

## 查看系统资源占用

```bash
top -d 0.1
```

## 查看 syslog

```bash
tail -f -n 5 /var/log/syslog
```

## vscode 常用快捷键
多行选中 shift+Tab 同时向左移动

## core dump 生成core文件，查看程序崩溃位置

```bash
ulimit -c unlimited
gdb executable core
bt
```



