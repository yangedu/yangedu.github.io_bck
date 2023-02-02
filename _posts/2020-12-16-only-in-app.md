---
layout: post
title:  "只允许在app中访问"
date:   2020-12-16 14:18:00 +0800
categories: php
tags: 总结
author: 葩木乐
description: 对访问方式做特殊过滤
---  

### 需求  
普通的h5页面只允许在指定的app内部访问，禁止在外部的浏览器中访问  
~~~  
1. app 在usergent中添加特定的识别信息  
2. 页面中获取useragent信息，根据过滤出指定的识别信息来执行特定的业务流程
使用到的变量  $userAgent = $_SERVER['HTTP_USER_AGENT']  
函数 区分大小写strpos($userAgent,'识别码') === false  
不区分大小写 stripos($userAgent,'识别码')
其中识别码是app中自定义，需要和手机端开发者配合定义。
~~~
但是有个缺点，就是自定义的识别码如果在userAgent中部分代码重复了就判断错误，自定义时尽量避免较短且常见的信息。