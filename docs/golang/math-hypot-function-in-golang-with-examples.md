# Golang 中的 Math.Hypot 函数及其示例

> Original: [https://www.geeksforgeeks.org/math-hypot-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-hypot-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在数学包的帮助下对数字执行运算。 您可以借助**数学包**提供的**Hypt()函数**找到斜边，即 sqrt(a*a+b*b)。 因此，您需要在 import 关键字的帮助下在程序中添加一个数学包，才能访问 supt()函数。

**语法：**

```go
func Hypot(a, b float64) float64
```

*   如果您在此函数中传递+inf 或-inf，如 supt(+inf，b)或 supt(-inf，b)，则此函数将返回+inf。
*   如果您在此函数中传递+inf 或-inf，如 supt(a，+inf)或 supt(a，-inf)，则此函数将返回-inf。
*   如果您在此函数中传递 NaN，如 supt(NaN，b)或 supt(a，NaN)，则此函数将返回 NaN。

**示例 1：**

```go
// Golang program to illustrate hypot() function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding hypotenuse
    // Using Hypot() function
    res_1 := math.Hypot(3, 4)
    res_2 := math.Hypot(-2, 6)
    res_3 := math.Hypot(4, math.Inf(1))
    res_4 := math.Hypot(math.NaN(), 5)

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
    fmt.Printf("\nResult 4: %.1f", res_4)

}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1: 5.0
Result 2: 6.3
Result 3: +Inf
Result 4: NaN

```

**示例 2：**

```go
// Golang program to illustrate hypot() function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding hypotenuse
    // Using Hypot() function
    nvalue_1 := math.Hypot(3, 4)
    nvalue_2 := math.Hypot(-2, 6)
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.5f + %.5f = %.5f",
            nvalue_1, nvalue_2, res)

}
```

发帖主题：Re：Колибри0.7.0

```go
5.00000 + 6.32456 = 11.32456
```