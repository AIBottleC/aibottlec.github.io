---
layout: post
categories: web前端
date: 2016-11-17
comments: trues
title: "javascript和jquery基本元素操作对比"
---

* content
{:toc}

#### 如果我要创建一个div元素。

1. 使用DOM对象创建：

    使用document.createElement('div')方法创建元素。
2. 使用JQuery创建：

    使用$('<div>通过JQuery创建的新元素</div>')的方法直接创建元素。
#### 如果需要将id是‘div2js'的div元素删除。
 1. 使用DOM对象
 
     首先需要找到被删元素的父元素，通过父元素将其需要删除的子元素删除。
      +  var el = document.getElementById('div2js');
      +  el.parentNode.removeChild(el);
 2. 使用JQuery
 
      直接找到并删除。
        
      $('#div2js').remove();

#### 几个容易混淆的用法：

1. innerHtml是标签内的文本,输入输出到该DOM内部纯HTML代码(流);

(获得td、div等html元素时候,它们是没有value或是text属性,只能用innerHtml)
2. value是表单元素特有的属性,输入输出的是转义文本(字符串);

    (Button、CheckBox、Radio)随表单一起发送的值;
    
    (Reset、Submit)标签;
    
    (Text、Hidden)默认值;
    
    (File、Password)
    
    (注: Text控件用value有效)
3. html和text都是jQuery/zepto的方法，只对jq对象有用-->
