---
{"dg-publish":true,"permalink":"//go/go-interface/"}
---

- 接口把所有的具有共性的方法定义在一起，任何其他类型只要实现了这些方法就是实现了这个接口。
- 接口可以让我们将不同的类型绑定到一组公共的方法上，从而实现多态和灵活的设计。
- Go 语言中的接口是隐式实现的，也就是说，如果一个类型实现了一个接口定义的所有方法，那么它就自动地实现了该接口。

```go
/* 定义接口 */
type interface_name interface {
   method1 [return_type]
   method2 [return_type]
   method3 [return_type]
   ...
   methodn [return_type]
}

/* 定义结构体 */
type 结构名 struct {
   /* variables */
}

/* 实现接口方法 */
func (结构变量 结构名) method1() [return_type] {
   /* 方法实现 */
}

func (结构变量 结构名) methodn() [return_type] {
   /* 方法实现*/
}
```

---

代码实例：

```go
package main

import "fmt"

type Shape interface {
    area() float64
}

type Rectangle struct {
    width  float64
    height float64
}

func (r Rectangle) area() float64 {
    return r.width * r.height
}

type Circle struct {
    radius float64
}

func (c Circle) area() float64 {
    return 3.14 * c.radius * c.radius
}

func main() {
    var s Shape

    s = Rectangle{width: 10, height: 5}
    fmt.Printf("矩形面积: %f\n", s.area())

    s = Circle{radius: 3}
    fmt.Printf("圆形面积: %f\n", s.area())
}
```