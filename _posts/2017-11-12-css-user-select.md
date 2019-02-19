---
layout: post
title:  css user-select 막기
date:   2017-11-12 00:00:00 +0800
categories: css
tag: css
---

* content
{:toc}


텍스트 드레그 막기
====================================
```
/*user-select:none 속성은 해당요소의 드레그, 더블클릭, 블럭지정을 막는다.*/
p {
   -ms-user-select: none; 
   -moz-user-select: -moz-none;
   -khtml-user-select: none;
   -webkit-user-select: none;
   user-select: none;
 }
```