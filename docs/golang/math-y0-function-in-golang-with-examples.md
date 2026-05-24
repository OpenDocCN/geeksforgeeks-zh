# 数学。Y0()在 Golang 中的作用举例

> 原文:[https://www . geesforgeks . org/math-y0-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-y0-function-in-golang-with-examples/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助数学包提供的 **Y0()函数**，可以找到第二类零阶贝塞尔函数。因此，您需要借助 import 关键字在程序中添加一个数学包来访问 Y0()函数。

**语法:**

```go
func Y0(a float64) float64
```

*   如果在这个函数中像 Y0(+Inf)一样传递+Inf，那么这个函数将返回 0。
*   如果在这个函数中像 Y0(0)一样传递 0，那么这个函数将返回-Inf。
*   如果 a 的值< 0，那么这个函数将返回 NaN。
*   如果在这个函数中像 Y0(NaN)一样传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate
// the use of math.Y0() function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the order-zero Bessel
    // function of the second kind
    // Using Y0() function
    res_1 := math.Y0(-3)
    res_2 := math.Y0(6)
    res_3 := math.Y0(math.Inf(1))
    res_4 := math.Y0(math.NaN())
    res_5 := math.Y0(4.6)
    res_6 := math.Y0(0)

    // Displaying the result
    fmt.Println("Result 1: ", res_1)
    fmt.Println("Result 2: ", res_2)
    fmt.Println("Result 3: ", res_3)
    fmt.Println("Result 4: ", res_4)
    fmt.Println("Result 5: ", res_5)
    fmt.Println("Result 6: ", res_6)

}
```

**输出:**

```go
Result 1:  NaN
Result 2:  -0.28819468398157916
Result 3:  0
Result 4:  NaN
Result 5:  -0.22345995255364678
Result 6:  -Inf

```

**例 2:**

```go
// Golang program to illustrate
// the use of math.Y0() function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the order-zero Bessel
    // function of the second kind
    // Using Y0() function
    nvalue_1 := math.Y0(5.89)
    nvalue_2 := math.Y0(5)

    // Sum of the given numbers
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.3f + %.3f = %.3f",
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
-0.306 + -0.309 = -0.614
```