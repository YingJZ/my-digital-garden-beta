---
{"dg-publish":true,"permalink":"///html/html-head/"}
---

可以添加在头部区域的元素标签为: `<title>`, `<style>`, `<meta>`, `<link>`, `<script>`, `<noscript>` 和 `<base>`。

- `<title>` 定义了文档的标题：`<title>编程狮(w3cschool.cn)</title>`
- `<base>` 标签描述了基础的链接地址/链接目标，该标签为HTML文档中所有的链接规定**默认地址**或**默认目标**（`target`）。例如：
```html
<base href="//www.w3cschool.cn/images/" target="_blank">
```
- `<meta>` 标签提供关于HTML文档的元数据。元数据不会显示在页面上，但对于机器是可读的。一般来说，meta元素被用于给出页面的描述、关键词、文档的作者、最后修改时间以及其他元数据。元数据可用于浏览器（如何显示内容或重新加载页面），搜索引擎（关键词）等。
```html
<meta name="description" content="Free Web tutorials on HTML, CSS, XML" />
<meta name="keywords" content="HTML, CSS, XML" />
```
- `<link>` 标签确定了文档与外部资源之间的关系。通常用于链接到样式表（引入**外部** css 文件）：
```html
<link rel="stylesheet" type="text/css" href="mystyle.css">
```
- `<style>` 标签在 html 文档内**定义样式信息**（或**覆盖**外部样式表中的信息）
