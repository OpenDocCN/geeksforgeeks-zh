# Golang 中的 Math.Inf()函数，示例为

> Original: [https://www.geeksforgeeks.org/math-inf-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-inf-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在数学包的帮助下对数字执行运算。 您可以找到数学包提供的正无穷大(if sign>=0)或负无穷大(if sign< 0) with the help of the **inf()函数**。 因此，您需要在 IMPORT 关键字的帮助下在程序中添加一个数学包来访问 inf()函数。
**语法：**和

```go
func Inf(sign int) float64
```

**示例 1：**

## 电容 / 碳

```go
// Golang program to illustrate the
// math.Inf() Function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding positive infinity
    // and negative infinity
    // Using Inf() function
    res_1 := math.Inf(-1)
    res_2 := math.Inf(1)

    // Displaying the result
    fmt.Println("Result 1: ", res_1)
    fmt.Println("Result 2: ", res_2)

}
```

发帖主题：Re：Колибри0.7.8.0

```go
Result 1: -Inf
Result 2: +Inf
```

**示例 2：**

## 电容 / 碳

```go
// Golang program to illustrate the
// math.Inf() Function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding positive infinity
    // and negative infinity
    // Using Inf() function
    nvalue := math.Inf(2)
    mvalue := math.Inf(-3)

    fmt.Println("Positive infinity: ", nvalue)
    fmt.Println("Negative infinity: ", mvalue)

}
```

发帖主题：Re：Колибри0.7.8.0

```go
Positive infinity:  +Inf
Negative infinity:  -Inf
```