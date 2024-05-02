---
{"dg-publish":true,"permalink":"//go/array-vs-slice/"}
---

```go
// 数组（Array）类型的大小在编译时即确定
var a4 [4] int              // 有4个int变量的数组，初始为0
a3 := [...]int{3, 1, 5}     // 有3个int变量的数组，同时进行了初始化

// Array和slice各有所长，但是slice可以动态的增删，所以更多时候还是使用slice。
s3 := []int{4, 5, 9}    // 回去看看 a3 ，是不是这里没有省略号？
s3 = append(s3, 4, 5, 6)  // 向slice中增加元素
s4 := make([]int, 4)    // 分配4个int大小的内存并初始化为0
var d2 [][]float64      // 这里只是声明，并未分配内存空间
bs := []byte("a slice") // 进行类型转换

// 还可以用如下方法传递一个slice常量或变量，并在后面加上省略号，
// 用以表示我们将引用一个slice、解包其中的元素并将其添加到s数组末尾。
s = append(s, []int{7, 8, 9}...) // 第二个参数是一个slice常量
```

