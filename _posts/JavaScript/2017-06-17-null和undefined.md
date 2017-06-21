---
layout: post
title:  "null和undefined"
categories: JavaScript
comments: true
---

#### null和undefined
##### 相似之处
都是完全不可变的，没有属性和方法，也不能给其属性赋值。事实上,试图访问或定义一个属性将会引发一个类型错误（TypeError）。正如他们的名字暗示的那样，他们是完全无效的值。
    
```javascript
console.log(Boolean(null));//false
console.log(Boolean(undefined));//false
console.log(null == undefined);//true
console.log(null === undefined);//false
console.log(null == 0);//false
console.log(undefined == 0);//false
console.log(false == 0);//true
console.log("" == 0);//true
```

ECMAScript认为undefined是从null派生出来的，所以把它们定义为相等的。

##### 不同之处
 1. undefined代表不存在的值。通常在试图访问一个不存在的值时，在JavaScript这种动态的弱类型语言中，只会默认返回一个undefined值，而不是上升为一个错误。
    - 任何声明变量时没有提供一个初始值，都会有一个为undefined的默认值
    `var foo; // 默认值为 undefined`

    - 当试图访问一个不存在的对象属性或数组项时，返回一个undefined值
    ```
    var array = [1, 2, 3];
    var foo = array.foo; // foo 属性不存在, 返回 undefined
    var item = array[5]; // 数组中没有索引为5的项，返回 undefined
    ```

    - 如果省略了函数的返回语句,返回undefined
    `var value = (function(){})(); // 返回 undefined`

    - 函数调用时未提供值的参数值,结果将为undefined
    ```
    (function(undefined){
        // 参数是 undefined
        })();
    ```

    - undefined是一个预定义的全局变量，初始化为undefined值(不像null关键字)
    `'undefined' in window; // true`

    - undefined参与任何数值计算时，其结果一定是NaN。
     
 2. null通常用作一个空引用一个空对象的预期,就像一个占位符。
    - typeof操作符作用于null值时返回“object”，虽然提出了修正，后出于兼容的目的，这一点已经保持不变。 
        
    - DOM是独立于语言的，不属于ECMAScript规范的范围。因为它是一个外部API，试图获取一个不存在的元素返回一个null值，而不是undefined。（getElementById和querySelector符合)。null用来表示尚未存在的对象。
        
    - 通过分配null值，可以有效地清除引用，并假设对象没有引用其他代码，指定垃圾收集，确保回收内存。
    - null 参与数值运算时其值会自动转换为 0
 


