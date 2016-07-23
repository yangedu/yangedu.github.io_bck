---
layout: post
title: 开始：oschina和github并行之路
category: git
tags: github
keywords: git,github,oschina
description: 多版本库并行，实现一个代码多个地方并存，保证代码的备份功能
---  
### 需求  
在写这篇文章的时候，仍觉得这是个蛋疼的需求~  
最初一个同事领着进入到oschina开源中国，注册了帐号（当时还用俩邮箱注册搞的好混乱），在使用了一段时间后又接触了github，对于开源中国和github的优缺点没有太大的区分，现在感觉到的是开源中国上的版本库可以私有，github上可以建立个**高大上**的博客...能力和使用时间关系，其他的暂时没有用出区别来。  
然后还是想把一个版本分存在两个站点上，不为啥，就是想这么做。  

### 步骤  
这个也是在别人有先例的基础上做的  
1. 在github上创建版本库。  
2. 在开源中国导入该版本库。（导入之后你可以做些调整，我就把这个库变成了私有）  
3. 在本地先clone下来github的库。  
4. 先复制一下开源中国上的库地址，如果是你自己的电脑，建议使用ssh格式的，那样就不用每次提交时输入帐号密码了，如果是公共的，可以使用https格式的。  
5. 在库文件夹中打开git,增加新的远程库地址  `git remote add origin-os [库地址]`  
6. 最后一步就是更新的时候更新两个库就可以了，我现在用的笨法子，先在编辑器中通过界面提交到github的版本库，然后在文件夹中打开git,手动push 到开源中国上。当然也可以全部通过git提交。执行的两个操作是：  
 `git push origin master`  
 `git push origin-os master`  
7. 拉取远程版本库方法，默认的是 `git pull` 是默认拉取github的版本库（也可以`git pull origin master`),但是拉取另外一个开源中国上的就要写全了，`git pull origin-os master`。如果仅仅拉取远程库(`git pull origin-os`)则不成功。  
8. 在搜到的一位高人，他有说创建一个脚本p,p的内容就是上面的两次提交，然后执行p就可以了，`chmod +x p & p` ,可惜我知识水平有限，暂时无法创建他说的脚本和执行。来源：[开源项目中如何同时支持Git@OSC和Github](http://my.oschina.net/apdplat/blog/415849 "开源项目中如何同时支持Git@OSC和Github")  

### 结语  
1. 好像就是创建不同的远程库，然后提交两次
2. 如果你的开源中国和github帐号一致，提交时用户名啥的会比较省心，因为这样提交上去一般不会出现名字错误。如果不同的话，提交者名字就只能以一个库为准了。
3. 创建远程库错误时，可以用`git remote rm origin-os`删除就行，然后重新创建  

### 选张图床上的摄影结束吧
现在打算使用网易的lofter.com来做图床，不知道后期会有啥潜在的问题，阿门~  
![自来也，纲手姬，大蛇丸](http://imglf0.nosdn.127.net/img/Wk9RdWc3UUVnQWI3ZVkrSnd3TW5zZFpLMWkrYlpEK2RGR2gzbmVPbE1JRUhJKzBZS2ZkMDd3PT0.jpg?imageView&thumbnail=1680x0&quality=96&stripmeta=0&type=jpg)  
![dota2](http://imglf2.nosdn.127.net/img/VFNNRXpSdUdncmVqYitaVkxsRU9QaDFiM1lBTFY4RDhOc2k5T3NkMENTNURqSmhBYmQ4NElRPT0.gif)
