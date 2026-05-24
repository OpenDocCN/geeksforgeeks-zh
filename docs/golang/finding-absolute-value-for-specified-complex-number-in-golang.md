# 求 Golang 中指定复数的绝对值？

> 原文:[https://www . geeksforgeeks . org/find-指定复数的绝对值-in-golang/](https://www.geeksforgeeks.org/finding-absolute-value-for-specified-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。您可以借助*数学/cmplx 软件包*提供的 **Abs()函数**找到指定复数的绝对值。因此，您需要在 import 关键字的帮助下在程序中添加一个 math/cmplx 包来访问 Abs()函数。

**语法:**

```go
func Abs(a complex128) float64
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate
// how to find absolute value
package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding absolute value of
    // the specified complex number
    // Using Abs() function
    res_1 := cmplx.Abs(3 + 5i)
    res_2 := cmplx.Abs(-4 + 8i)
    res_3 := cmplx.Abs(-8 - 7i)

    // Displaying the result
    fmt.Println("Random Number 1:", res_1)
    fmt.Println("Random Number 2: ", res_2)
    fmt.Println("Random Number 3: ", res_3)
}
```

**输出:**

```go
Random Number 1: 5.8309518948453
Random Number 2:  8.94427190999916
Random Number 3:  10.63014581273465

```

**例 2:**

```go
// Golang program to illustrate how
// to find absolute value
package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Complex numbers
    cnumber_1 := complex(5, 7)
    cnumber_2 := complex(6, 9)

    // Finding absolute values
    absvalue_1 := cmplx.Abs(cnumber_1)
    absvalue_2 := cmplx.Abs(cnumber_2)

    // Sum of two absolute values
    res := absvalue_1 + absvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Println("Complex Number 2: ", cnumber_2)
    fmt.Println("Sum of the absolute values of "+
                   "the given complex numbers: ")

    fmt.Printf("%.1f + %.1f = %.1f", absvalue_1, absvalue_2, res)

}
```

**输出:**

```go
Complex Number 1:  (5+7i)
Complex Number 2:  (6+9i)
Sum of the absolute values of the given complex numbers: 
8.6 + 10.8 = 19.4

```