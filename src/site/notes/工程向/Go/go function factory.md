---
{"dg-publish":true,"permalink":"//go/go-function-factory/"}
---

函数工厂（Function Factory）是指**返回值为另一个函数**的函数

```go
func calculatorFactory(operator string) func(int, int) int {
	switch operator {
	case "+":
		return func(a, b int) int { return a + b }
	case "-":
		return func(a, b int) int { return a - b }
	case "*":
		return func(a, b int) int { return a * b }
	case "/":
		return func(a, b int) int { return a / b }
	default:
		return nil
	}
}

func main() {
	add := calculatorFactory("+")
	subtract := calculatorFactory("-")
	multiply := calculatorFactory("*")
	divide := calculatorFactory("/")

	fmt.Println(add(5, 3))      // 输出：8
	fmt.Println(subtract(10, 4)) // 输出：6
	fmt.Println(multiply(6, 7))  // 输出：42
	fmt.Println(divide(15, 3))   // 输出：5
}
```