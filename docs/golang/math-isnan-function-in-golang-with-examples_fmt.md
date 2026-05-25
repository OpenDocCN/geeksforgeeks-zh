# Golang 中的 `math.IsNaN()` 函数示例

> Original: [https://www.geeksforgeeks.org/math-isnan-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-isnan-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在 `math` 包的帮助下对数字执行运算。此包提供 `IsNaN()` 函数，用于检查 `x` 是否为 IEEE754 “非数字”值。如果 `x` 是 IEEE 754 “非数字”值，则此函数返回 `true`。否则，此函数将返回 `false`。因此，需要在 `import` 关键字的帮助下在程序中添加一个 `math` 包来访问 `IsNaN()` 函数。

## 语法

```go
func IsNaN(x float64) (is bool)
```

## 示例 1

```go
// Golang program to illustrate 
// math.IsNaN() Function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

// Checking the specified value
// is not-a-number or not
// Using IsNaN() function
a1 := 4.4
res1 := math.IsNaN(a1)
fmt.Println("Result 1:", res1)

a2 := math.NaN()
res2 := math.IsNaN(a2)
fmt.Println("Result 2:", res2)    
}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1: false
Result 2: true
```

## 示例 2

```go
// Golang program to illustrate 
// math.IsNaN() Function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

// Checking the specified value 
// is not-a-number or not
// Using IsNaN() function
a := math.NaN()
res := math.IsNaN(a)
if (res == true){
    fmt.Println("a is not-a-number")
}else{
fmt.Println("a is not a NaN(not-a-number)")    
} 
}
```

发帖主题：Re：Колибри0.7.0

```go
a is not-a-number
```