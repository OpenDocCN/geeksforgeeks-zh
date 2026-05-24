# Golang 中的 Math.Dim()函数，示例

> Original: [https://www.geeksforgeeks.org/math-dim-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-dim-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在数学包的帮助下对数字执行运算。 **数学包提供的 Dim()函数**返回 a-b 或 0 的最大值*。 因此，要访问此函数，您需要在程序中借助 IMPORT 关键字添加一个数学包。*

**语法：**

```go
 func Dim(a, b float64) float64
```

*   如果在此函数中传递 inf，如 Dim(+inf，+inf)，则此函数将返回 NaN。
*   如果在此函数中传递-inf，如 Dim(-inf，-inf)，则此函数将返回 NaN。
*   如果在此函数中传递 NaN，如 Dim(a，NaN)或 Dim(NaN，b)，则此函数将返回 NaN。

**示例 1：**

```go
// Golang program to illustrate the dim function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Using Dim() function
    res_1 := math.Dim(2, -3)
    res_2 := math.Dim(8, -1)
    res_3 := math.Dim(-4, -2)

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)

}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1: 5.0
Result 2: 9.0
Result 3: 0.0

```

**示例 2：**

```go
// Golang program to illustrate the dim function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Using Dim() function
    nvalue_1 := math.Dim(3, -1)
    nvalue_2 := math.Dim(4, 3)
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.1f + %.1f = %.1f",
            nvalue_1, nvalue_2, res)

}
```

发帖主题：Re：Колибри0.7.0

```go
4.0 + 1.0 = 5.0
```