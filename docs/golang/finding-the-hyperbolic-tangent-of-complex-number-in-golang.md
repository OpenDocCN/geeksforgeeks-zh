# 求 Golang 中复数的双曲正切

> 原文:[https://www . geeksforgeeks . org/golang 中求复数的双曲正切/](https://www.geeksforgeeks.org/finding-the-hyperbolic-tangent-of-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。您可以借助数学/cmplx 包提供的 **Tanh()函数**找到指定复数的双曲正切值。因此，您需要在 import 关键字的帮助下在程序中添加一个 math/cmplx 包来访问 Tanh()函数。

**语法:**

```go
func Tanh(y complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1 :**

```go
// Golang program to illustrate how to find the
// hyperbolic tangent of the specified complex
// number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding hyperbolic tangent of 
    // the specified complex number
    // Using Tanh() function
    res_1 := cmplx.Tanh(1 + 5i)
    res_2 := cmplx.Tanh(-2 + 8i)
    res_3 := cmplx.Tanh(-1 - 2i)

    // Displaying the result
    fmt.Println("Result 1: ", res_1)
    fmt.Println("Result 2: ", res_2)
    fmt.Println("Result 3: ", res_3)
}
```

**输出:**

```go
Result 1:  (1.2407479829240697-0.1861094776473042i)
Result 2:  (-1.0356479469632376-0.010925884335752532i)
Result 3:  (-1.16673625724092+0.24345820118572523i)

```

**例 2 :**

```go
// Golang program to illustrate how to find the
// hyperbolic tangent of the specified complex
// number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(0, 2)
    cnumber_2 := complex(4, 6)

    // Finding hyperbolic tangent
    cvalue_1 := cmplx.Tanh(cnumber_1)
    cvalue_2 := cmplx.Tanh(cnumber_2)

    // Sum of two hyperbolic tangent values
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Println("Hyperbolic tangent 1: ", cvalue_1)

    fmt.Println("Complex Number 2: ", cnumber_2)
    fmt.Println("Hyperbolic tangent 2: ", cvalue_2)
    fmt.Println("Sum : ", res)

}
```

**输出:**

```go
Complex Number 1:  (0+2i)
Hyperbolic tangent 1:  (0-2.185039863261519i)
Complex Number 2:  (4+6i)
Hyperbolic tangent 2:  (0.9994339325466381-0.0003597965782916252i)
Sum :  (0.9994339325466381-2.1853996598398107i)

```