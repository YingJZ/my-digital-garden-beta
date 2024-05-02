---
{"dg-publish":true,"permalink":"///javascript/ajax/ajax/"}
---


## 什么是 AJAX？

AJAX = 异步 JavaScript 和 XML。

通过在后台与服务器进行少量数据交换，AJAX 可以使网页实现异步更新。这意味着可以在不重新加载整个网页的情况下，**对网页的某部分**进行更新。

## 创建 XMLHttpRequest（XHR） 对象

XMLHttpRequest 是 AJAX 的基础，用于在后台与服务器交换数据。

创建 XMLHttpRequest 对象的语法：

```javascript
variable = new XMLHttpRequest();
```

老版本的 Internet Explorer （IE5 和 IE6）使用 ActiveX 对象：

```javascript
variable = new ActiveXObject("Microsoft.XMLHTTP");
```

根据浏览器选择对象：

```javascript
var xmlhttp;
if (window.XMLHttpRequest)
{
    //  IE7+, Firefox, Chrome, Opera, Safari 浏览器执行代码
    xmlhttp=new XMLHttpRequest();
}
else
{
    // IE6, IE5 浏览器执行代码
    xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
}
```

## XHR 请求

```javascript
xmlhttp.open("GET","/try/ajax/demo_get.php",true);
xmlhttp.send();
```

| 方法 | 描述 |
| ---- | ---- |
| open(_method_,_url_,_async_) | 规定请求的类型、URL 以及是否异步处理请求。<br><br>-  _method_：请求的类型；GET 或 POST<br>-  _url_：文件在服务器上的位置<br>-  _async_：true（异步）或 false（同步）<br>==XMLHttpRequest 对象如果要用于 AJAX 的话，其 open() 方法的 async 参数必须设置为 true== |
| send(_string_) | 将请求发送到服务器。<br><br>- _string_：仅用于 POST 请求 |

TIP1：简单的 GET 请求，如 `xmlhttp.open("GET","/try/ajax/demo_get.php",true)`，可能得到的是缓存的结果。为了避免这种情况，可以用 POST 请求，或者向 URL 添加一个唯一的随机 ID：

```javascript
xmlhttp.open("GET","/try/ajax/demo_get.php?t=" + Math.random(),true);
xmlhttp.send();
```


TIP2：如果想在 POST 请求中添加 HTTP 头，可以使用 `setRequestHeader(header,value)` 函数：

```javascript
xmlhttp.open("POST","/try/ajax/demo_post2.php",true);
xmlhttp.setRequestHeader("Content-type","application/x-www-form-urlencoded");
xmlhttp.send("fname=Henry&lname=Ford");
```

TIP3：当使用 `async=true` 时，请规定在响应处于 [[工程向/前端/Javascript/AJAX/onreadystatechange\|onreadystatechange]] 状态时执行的函数：

```javascript
xmlhttp.onreadystatechange=function()
{
    if (xmlhttp.readyState==4 && xmlhttp.status==200)
    {
        document.getElementById("myDiv").innerHTML=xmlhttp.responseText;
    }
}
xmlhttp.open("GET","/try/ajax/ajax_info.txt",true);
xmlhttp.send();
```

--- 

> 不推荐使用 `async=false`，这会导致等到服务器响应就绪才继续执行。如果服务器繁忙或缓慢，应用程序会挂起或停止。注意：当您使用 `async=false` 时，请不要编写 `onreadystatechange` 函数——把代码放到 send() 语句后面即可：
```javascript
xmlhttp.open("GET","/try/ajax/ajax_info.txt",false);
xmlhttp.send();
document.getElementById("myDiv").innerHTML=xmlhttp.responseText;
```


## XHR 响应

如需获得来自服务器的响应，请使用 `XMLHttpRequest` 对象的 `responseText`（字符串形式） 或 `responseXML`（XML 形式） 属性。

（JSON 响应也用 `responseText` 获取）

```javascript
document.getElementById("myDiv").innerHTML=xmlhttp.responseText;

xmlDoc=xmlhttp.responseXML;
txt="";
x=xmlDoc.getElementsByTagName("ARTIST");
for (i=0;i<x.length;i++)
{
    txt=txt + x[i].childNodes[0].nodeValue + "<br>";
}
document.getElementById("myDiv").innerHTML=txt;
```


```javascript
function loadJSON()
{
  var xmlhttp;
  if (window.XMLHttpRequest)
  {
    xmlhttp=new XMLHttpRequest();
  }
  else
  {
    xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
  }
  
  xmlhttp.onreadystatechange=function()
  {
    if (xmlhttp.readyState==4 && xmlhttp.status==200)
    {
      var myArr = JSON.parse(this.responseText);
      myFunction(myArr)
    }
  }
  
  xmlhttp.open("GET","/try/ajax/json_ajax.json",true);
  xmlhttp.setRequestHeader("Content-Type", "application/json;charset=UTF-8");
  xmlhttp.send();
}
function myFunction(arr) {
  var out = "";
  var i;
  for(i = 0; i < arr.length; i++) {
    out += '<a href="' + arr[i].url + '">' + 
    arr[i].title + '</a><br>';
  }
 document.getElementById("myDiv").innerHTML=out;
}
```

发送 JSON 数据：

```javascript
xmlhttp.send(JSON.stringify({ "email": "admin@runoob.com", "response": { "name": "runoob" } }));
```
