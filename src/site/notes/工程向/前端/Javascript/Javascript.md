---
{"dg-publish":true,"permalink":"///javascript/javascript/","pinned":true}
---


基本语法：

常量（字面量）：
- 字符串可以用单引号或双引号 `"John Doe"` 或  `'John Doe'`
- **数组**：`[40, 100, 1, 5, 25, 10]`
- **对象（相当于字典）**：`{firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"}` 
- 函数：`function myFunction(a, b) { return a * b;}`

[[工程向/前端/Javascript/变量\|变量]]：用关键字 `var` 来定义变量，用 `=` 给变量赋值，**严格大小写**
- **定义**方法和 C 一样
- **作用域** 默认只区分全局和局部（函数内），默认不具有块作用域性，`let` 定义的变量才有块作用域性

运算符：
1. （和 C 语言一样）逻辑运算符有 `&&` `!=` 等，但是==**不要使用 `==` ！**==
2. `==`比较会自动转换数据类型再比较，很多时候，会得到非常诡异的结果；
3. `===`比较，它不会自动转换数据类型，如果数据类型不一致，返回`false`，如果一致，再比较
4. `NaN`这个特殊的Number与所有其他值都不相等，包括它自己：`NaN === NaN` 的取值为 `false`；唯一能判断`NaN`的方法是通过`isNaN()`函数。
5. 注意浮点数的相等比较：和其它语言相同，不能直接用 `===` （而是要通过绝对值之差判断）

[[工程向/前端/Javascript/数据类型（also 对象类型）\|数据类型（also 对象类型）]]：`16 + "Volvo"` 会得到结果 `16Volvo`

输出方式：
- 使用 **window.alert()** 弹出警告框。
- 使用  **document.write()** 方法将内容写到 HTML 文档中。
- 使用 **innerHTML** 写入到 HTML 元素。（配合 `document.getElementById("demo")` 使用）
- 使用 **console.log()** 写入到浏览器的控制台。

语句末分号 `;` —— 可选项；可以用于同一行多语句

对代码行进行折行：可以在文本字符串中使用反斜杠 `\` 对代码行进行换行：
```javascript
document.write("你好 \
世界!");
```
（但是下面的这种情况是错误的：
```javascript
document.write \ 
("你好世界!");
```

代码块：用 `{` 和 `}` 扩起来

注释：同 C（单行用 `//`，多行用 `/* */`）
