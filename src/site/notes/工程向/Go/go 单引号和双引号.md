---
{"dg-publish":true,"permalink":"//go/go/"}
---

Golang限定字符或者字符串一共三种引号，单引号 `‘’`，双引号 `""` 以及反引号 \` \` 。（反引号就是标准键盘“Esc”按钮下面的那个键。）

*对应的英文是：Single quote、Double quote、Back quote。*

- 单引号，表示 *byte* 类型或 *rune* 类型，对应 uint8和int32类型，**默认是 *rune* 类型**。（不能用来表示字符串）
	- **byte** 用来表示单个字节的数据
	- **rune** 用来表示 Unicode 的 code point 。
- 双引号，才是字符串
- 反引号，表示字符串**字面量**，不支持任何转义序列。
> 字面量 raw literal string 的意思是，你定义时写的啥样，它就啥样，你有换行，它就换行。你写转义字符，它也就展示转义字符


