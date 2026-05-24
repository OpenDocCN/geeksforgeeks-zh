# Golang 中的 math.ldexp()函数，示例

> Original: [https://www.geeksforgeeks.org/math-ldexp-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-ldexp-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在数学包的帮助下对数字执行运算。 此包提供**ldexp()函数**，该函数用于求 frexp 的逆。 或者换句话说，此函数返回 frac×2**exp。 因此，需要在 IMPORT 关键字的帮助下在程序中添加一个数学包来访问 Ldexp()函数。

**语法：**

```go
func Ldexp(frac float64, exp int) float64
```

*   如果 ldexp(±0，exp)，则此函数将返回±0。
*   如果 ldexp(±inf，exp)，则此函数将返回±inf。
*   如果 ldexp(NaN，exp)，则此函数将返回 NaN。

**示例 1：**

```go
// Golang program to illustrate 
// math.Ldexp() Function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the inverse of Frexp
    // Using Ldexp() function
    res_1 := math.Ldexp(1.1, 5)
    res_2 := math.Ldexp(math.Inf(-1), 2)
    res_3 := math.Ldexp(+0, 1)
    res_4 := math.Ldexp(2, 5)
    res_5 := math.Ldexp(math.NaN(), 1)

    // Displaying the result
    fmt.Printf("\nResult 1: %f", res_1)
    fmt.Printf("\nResult 2: %f", res_2)
    fmt.Printf("\nResult 3: %f", res_3)
    fmt.Printf("\nResult 4: %f", res_4)
    fmt.Printf("\nResult 5: %f", res_5)
}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1: 35.200000
Result 2: -Inf
Result 3: 0.000000
Result 4: 64.000000
Result 5: NaN

```

**示例 2：**

```go
// Golang program to illustrate
// math.Ldexp() Function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the inverse of Frexp
    // Using Ldexp() function
    nvalue_1 := math.Ldexp(2, 5)
    nvalue_2 := math.Ldexp(6, 2)

    // Finding the sum of inverse of Frexp
    res := nvalue_1 + nvalue_2
    fmt.Println("Result 1: ", nvalue_1)
    fmt.Println("Result 2: ", nvalue_2)
    fmt.Println("Sum of Result 1 and Result 2: ", res)

}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1:  64
Result 2:  24
Sum of Result 1 and Result 2:  88

```