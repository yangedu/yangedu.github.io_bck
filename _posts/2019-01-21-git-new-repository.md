---
layout: post
title:  "新创建git仓库的基本操作"
date:   2019-01-21 10:25:00 +0800
categories: git
tags: 总结
author: 葩木乐
description: git仓库创建之初，在本地的部分操作
---
git仓库创建之初，在本地的部分操作

~~~
Git global setup  

git config --global user.name "myname"  
git config --global user.email "myEmail@qq.com"  

Create a new repository  

git clone git@gitee.com:myrepository/repository.git  
cd repository  
touch README.md  
git add README.md  
git commit -m "add README"  
git push -u origin master  

Existing folder or Git repository  

cd existing_folder  
git init  
git remote add origin git@gitee.com:myrepository/repository.git  
git add .  
git commit  
git push -u origin master  

//更换远程库地址
1. 直接更换：git remote set-url origin url  
2. 删除之后添加新的  
git remote rm origin  
git remote add origin url  
3. 修改配置文件  
在.git文件夹中config配置文件修改 url
~~~
