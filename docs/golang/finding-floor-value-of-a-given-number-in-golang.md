# 在 Golang 中查找给定数字的楼层值

> 原文:[https://www . geesforgeks . org/find-floor-value-of-a-给定数字 in-golang/](https://www.geeksforgeeks.org/finding-floor-value-of-a-given-number-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。借助**数学包**提供的 **Floor()函数**，可以找到小于等于指定数的最大整数值。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Floor()函数。

**语法:**

```go
func Floor(y float64) float64
```

*   如果在这个函数中传递+Inf 或-Inf，那么这个函数将返回+Inf 或-Inf。
*   如果在此函数中传递+0 或-0，则此函数将返回+0 或-0。
*   如果在这个函数中传递 NaN，那么这个函数将返回 NaN。

**例 1:**

```go
// Golang program to find out the floor value

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the greatest integer value 
    // less than or equal to the
    // specified number
    // Using Floor() function
    res_1 := math.Floor(4.7)
    res_2 := math.Floor(-8.976)
    res_3 := math.Floor(0.687997)

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)

}
```

**输出:**

```go
Result 1: 4.0
Result 2: -9.0
Result 3: 0.0

```

**例 2:**

```go
// Golang program to find out the floor value

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the greatest integer value
    // less than or equal to the 
    // specified number
    // Using Floor() function
    nvalue_1 := 3.4556775
    nvalue_2 := 23.564646
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.5f + %.5f = %.5f",
             nvalue_1, nvalue_2, res)

    fmt.Println("\nGreatest integer value: ",
                             math.Floor(res))

}
```

**输出:**

```go
3.45568 + 23.56465 = 27.02032
Greatest integer value:  27

```