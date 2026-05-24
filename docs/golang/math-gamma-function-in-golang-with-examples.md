# Golang 中的 Math.Gamma()函数及其示例

> Original: [https://www.geeksforgeeks.org/math-gamma-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-gamma-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在数学包的帮助下对数字执行运算。 借助数学包提供的**Gamma()函数**，您可以找到给定值的 Gamma 函数。 因此，您需要在程序中添加一个数学包，并借助 import 关键字来访问 Gamma()函数。

**语法：**

```go
func Gamma(a float64) float64
```

*   如果 Gamma(+inf)，则此方法将返回+inf。
*   如果 Gamma(+0)，则此方法将返回+inf。
*   如果 Gamma(-inf)，则此方法将返回-inf。
*   如果 Gamma(A)，则对于整数 a<0，此方法将返回 NaN。
*   如果 Gamma(-inf)，则此方法将返回 NaN。
*   如果是 Gamma(NaN)，则此方法将返回 NaN。

**示例 1：**

```go
// Golang program to illustrate
// the math.Gamma() function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding gamma function 
    // of the given values.
    // Using Gamma() function
    res_1 := math.Gamma(math.Inf(-1))
    res_2 := math.Gamma(math.Inf(1))
    res_3 := math.Gamma(0)
    res_4 := math.Gamma(1)
    res_5 := math.Gamma(math.NaN())

    // Displaying the result
    fmt.Printf("\nResult 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
    fmt.Printf("\nResult 4: %.1f", res_4)
    fmt.Printf("\nResult 5: %.1f", res_5)
}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1: NaN
Result 2: +Inf
Result 3: +Inf
Result 4: 1.0
Result 5: NaN

```

**示例 2：**

```go
// Golang program to illustrate
// the math.Gamma() function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding gamma function
    // of the given values.
    // Using Gamma() function
    nvalue_1 := math.Gamma(2)
    nvalue_2 := math.Gamma(4)

    // Sum of the given numbers
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.2f + %.2f = %.2f",
           nvalue_1, nvalue_2, res)

}
```

发帖主题：Re：Колибри0.7.0

```go
1.00 + 6.00 = 7.00
```