# 求 Golang 中复数的反双曲正弦

> 原文:[https://www . geesforgeks . org/find-the-inverse-双曲线-正弦-复数 in-golang/](https://www.geeksforgeeks.org/finding-the-inverse-hyperbolic-sine-of-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。允许你借助数学/cmplx 包提供的 **Asinh()函数**求指定复数的反双曲正弦。所以，你需要在你的程序中添加一个*数学/cmplx 包*在 import 关键字的帮助下访问 Asinh()函数。

**语法:**

```go
func Asinh(x complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate how to find the
// Inverse Hyperbolic Sine of Complex Number
package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding inverse hyperbolic sine of
    // the specified complex number
    // Using Asinh() function
    res_1 := cmplx.Asinh(2 + 5i)
    res_2 := cmplx.Asinh(-9 + 8i)
    res_3 := cmplx.Asinh(-5 - 7i)

    // Displaying the result
    fmt.Println("Result 1:", res_1)
    fmt.Println("Result 2:", res_2)
    fmt.Println("Result 3:", res_3)
}
```

**输出:**

```go
Result 1: (2.37054853731792+1.184231684275022i)
Result 2: (-3.1817205225071747+0.7249311476979132i)
Result 3: (-2.8440976626506607-0.9473406443130534i)

```

**例 2:**

```go
// Golang program to illustrate how to find
// Inverse Hyperbolic Sine of Complex Number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(2, 3)
    cnumber_2 := complex(6, 8)

    // Finding inverse hyperbolic sine
    cvalue_1 := cmplx.Asinh(cnumber_1)
    cvalue_2 := cmplx.Asinh(cnumber_2)

    // Sum of two inverse 
    // hyperbolic sine values
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Println("Inverse hyperbolic sine 1: ", cvalue_1)

    fmt.Println("Complex Number 2: ", cnumber_2)
    fmt.Println("Inverse hyperbolic sine 2: ", cvalue_2)
    fmt.Println("Sum of inverse hyperbolic sines : ", res)

}
```

**输出:**

```go
Complex Number 1:  (2+3i)
Inverse hyperbolic sine 1:  (1.9686379257930964+0.9646585044076027i)
Complex Number 2:  (6+8i)
Inverse hyperbolic sine 2:  (2.995040217583994+0.9248902126310973i)
Sum of inverse hyperbolic sines :  (4.9636781433770905+1.8895487170387i)

```