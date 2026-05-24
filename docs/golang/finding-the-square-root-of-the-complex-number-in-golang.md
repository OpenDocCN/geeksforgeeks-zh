# 求 Golang 中复数的平方根

> 原文:[https://www . geesforgeks . org/golang 中求复数的平方根/](https://www.geeksforgeeks.org/finding-the-square-root-of-the-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。允许你借助数学/cmplx 包提供的 **Sqrt()函数**求指定复数的平方根。在这个函数中，选择 q，使得实数(q) > = 0，并且 imag(q)具有与 imag(y)相同的符号。因此，要访问 **Sqrt()函数**，您需要借助 import 关键字在程序中添加一个 math/cmplx 包。

**语法:**

```go
func Sqrt(y complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate how to find
// the square root of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding the square root of 
    // the specified complex number
    // Using Sqrt() function
    res_1 := cmplx.Sqrt(8 - 6i)
    res_2 := cmplx.Sqrt(-4 + 12i)
    res_3 := cmplx.Sqrt(-3 - 9i)

    // Displaying the result
    fmt.Printf("Result 1: %.2f", res_1)
    fmt.Printf("\nResult 2:  %.2f", res_2)
    fmt.Printf("\nResult 3:  %.2f", res_3)
}
```

**输出:**

```go
Result 1: (3.00-1.00i)
Result 2:  (2.08+2.89i)
Result 3:  (1.80-2.50i)

```

**例 2:**

```go
// Golang program to illustrate how to find
// the square root of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(0, 2)
    cnumber_2 := complex(4, 6)

    // Finding square root
    cvalue_1 := cmplx.Sqrt(cnumber_1)
    cvalue_2 := cmplx.Sqrt(cnumber_2)

    // Sum of the given square roots
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Printf("Square Root 1: %.1f", cvalue_1)

    fmt.Println("\nComplex Number 2: ", cnumber_2)
    fmt.Printf("Square Root: %.1f ", cvalue_2)
    fmt.Printf("\nSum : %.1f", res)

}
```

**输出:**

```go
Complex Number 1:  (0+2i)
Square Root 1: (1.0+1.0i)
Complex Number 2:  (4+6i)
Square Root: (2.4+1.3i) 
Sum : (3.4+2.3i)

```