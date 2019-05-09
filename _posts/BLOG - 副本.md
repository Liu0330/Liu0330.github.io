---
layout:     post
title:      Django-安装xadmin的方法及主要配置方法
subtitle:   
date:       2019-04-10
author:     LIU WANG
catalog: true
tags: Django
    - Markdown
---
    - [Tools](#tools)
<!-- MarkdownTOC -->



历经千辛万苦，终于实现了django2.1中xadmin的使用
被论坛里各路神仙带跑N次

准确说是几个小时

 直接colne https://github.com/Liu0330/xadmin

工作系统环境：win10+Python3.6.x+Django2.1.x+Xadmin2.0（注意2.2版本就不行！！！）

因此本系列教程均是以此组合为基础展开讲解。其他系统版本也基本适用，有小部分不兼容之处请自行测试。

 

一、Django及xadmin安装

可以使用pip命令进行安装，或者直接下载安装包用python命令安装：

pip install Django==2.1
其他的包在克隆的xadmin中的requirements.txt里
pip freeze > requirements.txt（不用这句 导出依赖库怕忘记所以我只是拿来自己看的）
安装requirements.txt依赖
pip install -r requirements.txt
由于xadmin2.0官方版本存在一些兼容性bug，笔者对其源码进行了部分改动

在装完官方版的Django和xadmin之后，将笔者的xadmin修复版本替换到xadmin的原安装目录下即可。

论坛神仙说的：运行:pip install xadmin 后报错，所以陷入深坑无法自拔

 

首先是安装
就直接安装 xadmin 目录都有

自己导入呗就
### 安装第三方模块
- pip install retrying
- 下载源码解码，进入解压后的目录，```python setup.py install```
- `***.whl` 安装方法 `pip install ***.whl`

然后切记

运行生成数据库和 迁移命令

python manage.py makemigrations

python manage.py migrate

 

此外，我们还要建立一个超级管理员帐号，设置好帐号密码邮箱信息

python3 manage.py createsuperuser
然后可以使用了，下面可以顺利的进入管理界面了

如果报了csrf错误 就把Settings.py文件中的

![img](https://img-blog.csdnimg.cn/20190502233514359.png)

这行注释掉

其次就是进入到了Xadmin界面啦

![img](https://img-blog.csdnimg.cn/20190502233627576.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxODU2ODE0,size_16,color_FFFFFF,t_70)



---------------------
