---
{"dg-publish":true,"permalink":"///javascript/number/"}
---

1. JavaScript不区分整数和浮点数，统一用Number表示，以下都是合法的Number类型：
```js
123; // 整数123
0.456; // 浮点数0.456
1.2345e3; // 科学计数法表示1.2345x1000，等同于1234.5
-99; // 负数
0xff00; // 十六进制整数
NaN; // NaN表示Not a Number，当无法计算结果时用NaN表示
Infinity; // Infinity表示无限大，当数值超过了JavaScript的Number所能表示的最大值时，就表示为Infinity
```

2. Javascript 中的整数和浮点数可以直接比较：`12.00 === 12`

3. JavaScript的整数最大范围不是 $±2^{63}$ ，而是 $±2^{53}$

要精确表示比 $2^{53}$ 还大的整数，可以使用内置的 ***BigInt*** 类型，它的表示方法：
1. 在整数后加一个`n`，例如`9223372036854775808n`
2. 使用`BigInt()`把 *Number* 或*字符串*转换成 *BigInt*
*BigInt* 可以正常进行加减乘除等运算，结果仍然是 *BigInt*，但不能把 *BigInt* 和 Number 放在一起运算