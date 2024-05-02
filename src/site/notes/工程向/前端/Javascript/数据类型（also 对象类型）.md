---
{"dg-publish":true,"permalink":"///javascript/also/"}
---


**值类型(基本类型)**：字符串（String）、数字([[工程向/前端/Javascript/Number\|Number]]，**只有一种普通数字类型**)、布尔(Boolean)、**空（`null`）**、未定义（`undefined`）、Symbol。

**引用数据类型（对象类型）**：对象(Object)、数组(Array)、函数(Function)，
还有两个特殊的对象：正则（RegExp）和日期（Date）。

动态类型：相同的变量可用作不同的类型

```js
var x;               // x 为 undefined
x = 5;               // 现在 x 为数字
var x = "John";      // 现在 x 为字符串
```

声明新变量时，可以使用关键词 "new" 来声明其类型：

```js
var carname=new String;  
var x=      new Number;  
var y=      new Boolean;  
var cars=   new Array; //数组 
var person= new Object;
```

## 数组 Array

**数组**的两种声明方式：
```js
[1, 2, 3.14, 'Hello', null, true];
new Array(1, 2, 3); // 创建了数组[1, 2, 3]
```

数组的调用方式：从 0 开始的索引

## 对象 Object

可以通过两种方式访问对象属性

```js
person.lastName;
person["lastName"];
```

可以在定义中加入函数，那么对应的调用方法为：

```js
name = person.fullName();
```


## 函数 Function

用 `function` 关键字定义：`function myFunction(a,b)`

用 `return` 退出：
- 如果要返回结果：`return value1+value2`
- 返回值是可选的，可以直接 `return` 退出：

```js
function myFunction(a,b) 
{ 
	if (a>b) 
	{ 
		return; 
	} 
	return a+b 
}
```