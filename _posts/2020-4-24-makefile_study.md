---
layout: post
title: 'makefile'
subtitle: 'makefile 学习'
date: 2020-4-14
author: 邱鹏
cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
tags:  makefile  函数
---
# 1.wildcard

wildcard会展开文件夹内的所有文件夹（一级），文件名
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
# 2.eval

eval 函数会解析并执行$(eval text)中text的命令
示例中是创建一个文件夹命令
```Makefile
define mkdir
hello:
	mkdir test_eval
endef
$(eval $(call mkdir))

```






