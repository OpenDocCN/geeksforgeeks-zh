# 数学。Y1()函数在 Golang 中的应用示例

> 原文:[https://www . geesforgeks . org/math-y1-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-y1-function-in-golang-with-examples/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助**数学包**提供的 **Y1()函数**，可以找到第二类一阶贝塞尔函数。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Y1()函数。

**语法:**

```go
func Y1(a float64) float64
```

*   如果在这个函数中像 Y1(+Inf)一样传递+Inf，那么这个函数将返回 0。
*   如果在这个函数中像 Y1(0)一样传递 0，那么这个函数将返回-Inf。
*   如果 a 的值< 0，那么这个函数将返回 NaN。
*   如果在这个函数中像 Y1(NaN)一样传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to illustrate
// the use of math.Y1() function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the order-one Bessel
    // function of the second kind
    // Using Y1() function
    res_1 := math.Y1(-3)
    res_2 := math.Y1(6)
    res_3 := math.Y1(math.Inf(1))
    res_4 := math.Y1(math.NaN())
    res_5 := math.Y1(4.6)
    res_6 := math.Y1(0)

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
Result 2:  -0.17501034430039827
Result 3:  0
Result 4:  NaN
Result 5:  0.2737452414709432
Result 6:  -Inf

```

**例 2:**

```go
// Golang program to illustrate
// the use of math.Y1() function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the order-one Bessel
    // function of the second kind
    // Using Y1() function
    nvalue_1 := math.Y1(0.89)
    nvalue_2 := math.Y1(6)

    // Sum of the given numbers
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.3f + %.3f = %.3f", 
            nvalue_1, nvalue_2, res)

}
```

**输出:**

```go
-0.883 + -0.175 = -1.058
```