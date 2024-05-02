---
{"dg-publish":true,"permalink":"///html/html/"}
---

- 使用 `target` 属性，你可以定义被链接的文档在何处显示（在新的窗口打开，还是在原有的窗口中打开）。    
	- 默认会在原有的窗口中打开。
	- 如果 `target="_blank"` ，文档就会在新窗口打开。
	- 如果 `target="_top"`，文档就能跳出框架打开
- `id` 属性可用于在一个 HTML 文档中创建书签标记（书签在页面上不显示）。HTML 链接可准确定位到某一页的某个书签位置，语法为 `<a href="test.html#tips">link</a>` 
```html
<a id="tips">Useful Tips Section</a> <!-- 在 HTML 文档中插入 ID -->

<a href="//www.w3cschool.cn/html_links.html#tips"> Visit the Useful Tips Section</a> <!-- 创建一个链接到"有用的提示 (id="tips"）部分 -->
```
- 空链接：指向链接后，鼠标变成手形，但单击后仍停留在当前页面。
```html
<a href="#">链接文字</a>
```

> [!attention]  请始终将正斜杠添加到子文件夹。
> 假如这样书写链接：`href="//www.w3cschool.cn/html"`，就会向服务器产生**两次** HTTP 请求。这是因为服务器会添加正斜杠到这个地址，然后创建一个新的请求，就像这样：`href="//www.w3cschool.cn/html/"`。


创建电子邮件链接：（2个例子）
```html
<a href="mailto:wangdangpeng@factzone.com?Subject=Hello%20again" target="_top">
发送邮件</a>

<a href="mailto:someone@example.com?cc=someoneelse@example.com&bcc=andsomeoneelse@example.com&subject=Summer%20Party&body=You%20are%20invited%20to%20a%20big%20summer%20party!" target="_top">发送邮件!</a>
```

可以看出，`href` 的格式为 `mailto:电子邮件地址?可选参数`    
可选参数中可以指定很多内容