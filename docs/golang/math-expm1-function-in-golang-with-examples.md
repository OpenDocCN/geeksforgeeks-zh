# Golang 中的 Math.Expm1 函数()，示例为

> Original: [https://www.geeksforgeeks.org/math-expm1-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-expm1-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在数学包的帮助下对数字执行运算。 在**数学包**提供的**Expm1()函数**的帮助下，可以求出指定数减 1 的以 e 为底的指数，即*e**a-1*。 因此，您需要借助 import 关键字在程序中添加一个数学包来访问 Expm1()函数。

**语法：**

```go
func Expm1(a float64) float64
```

*   如果在此函数中传递+inf，则此函数将返回+inf。
*   如果在此函数中传递-inf，则此函数将返回-1。
*   在此函数中，非常大的值溢出到-1 或+inf。
*   如果在此函数中传递 NaN，则此函数将返回 NaN。

**示例 1：**

```go
// Golang program to illustrate the Exmp1 function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Using Expm1() function
    res_1 := math.Expm1(4)
    res_2 := math.Expm1(-1)
    res_3 := math.Expm1(math.Inf(1))
    res_4 := math.Expm1(math.NaN())

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
    fmt.Printf("\nResult 4: %.1f", res_4)

}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1: 53.6
Result 2: -0.6
Result 3: +Inf
Result 4: NaN

```

**示例 2：**

```go
// Golang program to illustrate the Exmp1 function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Using Expm1() function
    nvalue_1 := math.Expm1(7.3)
    nvalue_2 := math.Expm1(-3)
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.1f + %.1f = %.1f",
            nvalue_1, nvalue_2, res)

}
```

发帖主题：Re：Колибри0.7.0

```go
1479.3 + -1.0 = 1478.3 
```