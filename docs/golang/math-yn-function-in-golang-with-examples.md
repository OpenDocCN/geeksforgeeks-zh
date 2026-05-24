# 数学。Yn()函数在 Golang 中的应用示例

> 原文:[https://www . geesforgeks . org/math-yn-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-yn-function-in-golang-with-examples/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助数学软件包提供的 **Yn()函数**，可以得到第二类 n 阶贝塞尔函数。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Yn()函数。

**语法:**

```go
func Yn(a int, b float64) float64
```

*   如果在这个函数中像 Yn(a，+Inf)一样传递+Inf，那么这个函数将返回 0。
*   如果 a≥0 的值像 Yn(a≥0，0)，那么这个函数将返回-Inf。
*   如果 b<0 的值像 Yn(a，b<0)，那么这个函数将返回 NaN。
*   如果 a<0 的值像 Yn(a<0，0)，那么这个函数将返回+Tnf(如果 a 是奇数)或-Inf(如果 a 是偶数)。
*   如果在这个函数中像 Yn(a，NaN)一样传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate
// the use of math.Yn() function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the order-n Bessel 
    // function of the second kind
    // Using Yn() function
    res_1 := math.Yn(-3, -2)
    res_2 := math.Yn(6, 3)
    res_3 := math.Yn(1, 1.1)
    res_4 := math.Yn(1, math.NaN())
    res_5 := math.Yn(-1, 0)

    // Displaying the result
    fmt.Println("Result 1: ", res_1)
    fmt.Println("Result 2: ", res_2)
    fmt.Println("Result 3: ", res_3)
    fmt.Println("Result 4: ", res_4)
    fmt.Println("Result 5: ", res_5)

}
```

**输出:**

```go
Result 1:  NaN
Result 2:  -5.436470340703773
Result 3:  -0.698119560067667
Result 4:  NaN
Result 5:  +Inf

```

**例 2:**

```go
// Golang program to illustrate
// the use of math.Yn() function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the order-n Bessel
    // function of the second kind
    // Using Yn() function
    nvalue_1 := math.Yn(3, 4)
    nvalue_2 := math.Yn(5, 6)

    // Sum of the given numbers
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.3f + %.3f = %.3f", 
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
-0.182 + -0.197 = -0.379
```