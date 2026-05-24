# Golang 中的 Math.Jn()函数，示例

> Original: [https://www.geeksforgeeks.org/math-jn-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-jn-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在数学包的帮助下对数字执行运算。 借助**数学包**提供的**Jn()函数**，您可以找到第一类-n 阶贝塞尔函数。 因此，您需要在程序中添加一个数学包，并借助 import 关键字访问 Jn()函数。

**语法：**

```go
func Jn(a int, b float64) float64
```

**示例 1：**

```go
// Golang program to illustrate
// the math.Jn() function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding order-n Bessel 
    // function of the first kind
    // Using Jn() function
    res_1 := math.Jn(1, math.Inf(-1))
    res_2 := math.Jn(3, math.Inf(1))
    res_3 := math.Jn(4, 5)
    res_4 := math.Jn(1, math.NaN())

    // Displaying the result
    fmt.Printf("\nResult 1: %.2f", res_1)
    fmt.Printf("\nResult 2: %.2f", res_2)
    fmt.Printf("\nResult 3: %.2f", res_3)
    fmt.Printf("\nResult 4: %.2f", res_4)

}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1: 0.00
Result 2: 0.00
Result 3: 0.39
Result 4: NaN

```

**示例 2：**

```go
// Golang program to illustrate
// the math.Jn() function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding order-n Bessel 
    // function of the first kind
    // Using Jn() function
    nvalue_1 := math.Jn(2, 3.3)
    nvalue_2 := math.Jn(4, 5.6)

    // Sum of the given numbers
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.2f + %.2f = %.2f",
           nvalue_1, nvalue_2, res)

}
```

发帖主题：Re：Колибри0.7.0

```go
0.48 + 0.39 = 0.87
```