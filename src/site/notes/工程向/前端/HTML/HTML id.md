---
{"dg-publish":true,"permalink":"///html/html-id/"}
---

HTML ​**id​ 属性**用于为HTML 元素指定**唯一**的 id
- 一个 HTML文档中**不能**存在多个有相同 id 的元素！
- id 属性的值**区分大小写**
- id 的作用：
	- CSS 中，用 `# + id` 来设置某个元素的样式
	- Javascript 中，用 `document.getElementById("myHeader")` 来访问某个元素
	- 创建书签用于让读者跳转至网页的特定部分

```html
<style> /* 设置 id 为 "myHeader" 的元素的样式 */ 
#myHeader { 
	background-color: lightblue; 
	color: black; 
	padding: 40px; 
	text-align: center; 
}
</style>

<script> /* 修改 id 为 "myHeader" 的元素的内容 */
function displayResult() {
  document.getElementById("myHeader").innerHTML = "Have a nice day!";
}
</script>
```
