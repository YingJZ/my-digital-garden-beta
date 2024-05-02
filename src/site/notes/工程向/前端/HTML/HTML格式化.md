---
{"dg-publish":true,"permalink":"///html/html/"}
---

- 斜体（着重文字）：`<em>` 和 `<b>`
- 粗体（加重语气）：`<strong>` 和 `<i>`
- 水平线：`<hr>`
- 换行：`<br />`
- 注释：`<!-- 这是一个注释 -->`
- 字体放大/缩小 `<big>` 和 `<small>`
- 上标  `<sup>`；下标 `<sub>`

`<pre>` 标签内的部分会保留连续的多个空格和换行【称为预期格式文本】（类似代码块）

**计算机输出**：
```html
<code>计算机输出</code>
<kbd>键盘输入</kbd>
<tt>打字机文本</tt>
<samp>计算机代码样本</samp>
<var>计算机变量</var>
```

**地址**：
```html
<address>
Written by <a href="mailto:webmaster@example.com">Jon Doe</a>.<br> 
Visit us at:<br>
Example.com<br>
Box 564, Disneyland<br>
USA
</address>
```

**缩写**：在某些浏览器中，当您把鼠标移至缩略词语上时，title 可用于展示表达的完整版本。对于 Netscape 6.2 中的 `abbr` 和 `acronym` 元素都有效。
```html
<abbr title="etcetera">etc.</abbr>
<acronym title="World Wide Web">WWW</acronym>
```


**文字从右到左显示**
```html
<p>该段落文字从左到右显示。</p>
<p><bdo dir="rtl">该段落文字从右到左显示。</bdo></p> 
```


## HTML 引文, 引用, 及标签指定义

|标签|描述|
|:--|:--|
|[`<abbr>`](https://www.w3cschool.cn/htmltags/tag-abbr.html)|定义缩写 |
|[`<address>`](https://www.w3cschool.cn/htmltags/tag-address.html)|定义地址|
|[`<bdo>`](https://www.w3cschool.cn/htmltags/tag-bdo.html)|定义文字方向|
|[`<blockquote>`](https://www.w3cschool.cn/htmltags/tag-blockquote.html)|定义长的引用|
|[`<q>`](https://www.w3cschool.cn/htmltags/tag-q.html)|定义短的引用语|
|[`<cite>`](https://www.w3cschool.cn/htmltags/tag-cite.html)|定义引用、引证|
|[`<dfn>`](https://www.w3cschool.cn/htmltags/tag-dfn.html)|定义一个定义项目。|
