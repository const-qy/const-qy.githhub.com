---
layout: post
title: 'makefile'
subtitle: 'makefile 学习'
date: 2020-4-14
author: 邱鹏
cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
tags:  makefile  函数
---
# <一>
```Makefile
SLASH	:= /  #定义slash变量
#搜索文件夹内的所有特定类型的文件
listf = $(filter $(if $(2),$(addprefix %.,$(2)),%),\
		  $(wildcard $(addsuffix $(SLASH)*,$(1))))

listf_cc = $(call listf,home,txt) #在home/ 下搜索所有的.txt文件
a = $(call listf_cc,home,txt)
test: 
	@echo $(listf_cc) 
```







