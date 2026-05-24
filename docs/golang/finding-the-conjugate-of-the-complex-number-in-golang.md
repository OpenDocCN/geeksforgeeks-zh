# 求 Golang 中复数的共轭

> 原文:[https://www . geesforgeks . org/golang 中复数共轭的寻找/](https://www.geeksforgeeks.org/finding-the-conjugate-of-the-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。允许你借助数学/cmplx 包提供的 **Conj()函数**找到指定复数的共轭。因此，您需要在 import 关键字的帮助下，在程序中添加一个 math/cmplx 包来访问 Conj()函数。

**语法:**

```go
func Conj(y complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate how to find
// conjugate of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding conjugate of the 
    // specified complex number
    // Using Conj() function
    res_1 := cmplx.Conj(5i)
    res_2 := cmplx.Conj(-1 + 12i)
    res_3 := cmplx.Conj(-7 - 9i)

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2:  %.1f", res_2)
    fmt.Printf("\nResult 3:  %.1f", res_3)
}
```

**输出:**

```go
Result 1: (0.0-5.0i)
Result 2: (-1.0-12.0i)
Result 3: (-7.0+9.0i)

```

**例 2:**

```go
// Golang program to illustrate how to find
// conjugate of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(0, 2)
    cnumber_2 := complex(1, 6)

    // Finding conjugate of the
    // given complex numbers
    cvalue_1 := cmplx.Conj(cnumber_1)
    cvalue_2 := cmplx.Conj(cnumber_2)

    // Sum of the given values
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Printf("Conjugate 1: %.1f", cvalue_1)

    fmt.Println("\nComplex Number 2: ", cnumber_2)
    fmt.Printf("Conjugate 2: %.1f ", cvalue_2)
    fmt.Printf("\nSum : %.1f", res)

}
```

**输出:**

```go
Complex Number 1:  (0+2i)
Conjugate 1: (0.0-2.0i)
Complex Number 2:  (1+6i)
Conjugate 2: (1.0-6.0i) 
Sum : (1.0-8.0i)

```