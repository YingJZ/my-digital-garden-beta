---
{"dg-publish":true,"permalink":"///html/html/","pinned":true}
---


HTML 文档第一行用 `<!DOCTYPE html>` 声明这是一个 HTML 文档

在 head 部分用 `<meta charset="UTF-8">` 来解决**中文乱码**问题

---

**常用格式化标签**：
- 斜体（着重文字）：`<em> ... </em>`    `<b> ... </b>`
- 粗体（加重语气）：`<strong> ... </strong>`  `<i> ... </i>`
- 水平线：`<hr>`
- 换行：`<br />`
- 注释：`<!-- 这是一个注释 -->`
[[工程向/前端/HTML/HTML格式化\|更多格式化标签]] 

---

**属性**是为 ​`HTML`​ 元素提供的附加信息，一般形式：`name="value"`
> 在某些个别的情况下，比如属性值本身就含有双引号，那么必须使用单引号，例如：`name='John "ShotGun" Nelson'`

[[工程向/前端/HTML/HTML全局属性\|HTML全局属性]]

---

**[[工程向/前端/HTML/HTML链接\|HTML链接]]**

---

[[工程向/前端/HTML/HTML id\|HTML id]]

---

[[工程向/前端/HTML/HTML head\|HTML head]]

---

HTML entity name（[HTML 符号实体](https://www.w3cschool.cn/html/html-vcy63gdz.html))）即特殊符号的转义字符

---

## 图像

```html
<img src="图片.jpg" alt="替代文本" width="304" height="228" border = "3" align="right">
```  
其中，`border` 指定图像的边框宽度，`border=0` 时图片无边框。
（**在 HTML5 中已经废弃，可用 CSS 代替**）`align` 指定图片的对齐方式（`center` 居中，`right` 右侧）

[[工程向/前端/HTML/同一个图片的不同区域对应不同链接\|同一个图片的不同区域对应不同链接]]


## 表格

### 基本结构

- `<table>…</table>`：定义表格
- `<tr>…</tr>`：定义表格的行
- `<td>…</td>`：定义表格的列
- `<th>…</th>`：定义表格的标题栏（文字加粗）（可以实现水平/垂直标题）  

头部，主体和页脚的对应的三个标签是：
- `<thead>` - 创建单独的表头。
- `<tbody>` - 表示表格的主体。
- `<tfoot>` - 创建一个单独的表页脚。

### 表格空间：
- `cellspacing` 属性定义表格**单元格之间**的空间 
- `cellpadding` 属性表示单元格**边框**与单元格**内容**之间的距离

![Pasted image 20240127122307.png|325](/img/user/assets/Pasted%20image%2020240127122307.png)

### 合并单元格

行合并：`rowspan`   
列合并：`colspan`

```html
<table border = "1">
<tr>
	<th>Column 1</th>
	<th>Column 2</th>
	<th>Column 3</th>
</tr>
<tr>
	<td rowspan = "2">Row 1 Cell 1</td>
	<td>Row 1 Cell 2</td>
	<td>Row 1 Cell 3</td>
</tr>
<tr>
	<td>Row 2 Cell 2</td>
	<td>Row 2 Cell 3</td>
</tr>
<tr>
	<td colspan = "3">Row 3 Cell 1</td>
</tr>
</table>
```

效果如下：（关注 **Row1 Cell1** 和 **Row3 Cell1**）

![Pasted image 20240127175130.png|319](/img/user/assets/Pasted%20image%2020240127175130.png)


## 列表

### 无序列表

```html
<ul>  
	<li>Coffee</li>
	<li>Milk</li>
</ul>
```

### 有序列表

```html
<ol>       
	<li>Coffee</li>      
	<li>Milk</li>       
</ol>
```


### 