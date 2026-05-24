# 求 Golang 中复数的自然对数

> 原文:[https://www . geeksforgeeks . org/find-golang 中复数的自然对数/](https://www.geeksforgeeks.org/finding-the-natural-logarithm-of-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。允许你借助 math/cmplx 包提供的 **Log()函数**求指定复数的自然对数。因此，您需要借助 import 关键字在程序中添加一个 math/cmplx 包来访问 Log()函数。

**语法:**

```go
func Log(y complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate how to find the
// natural logarithm of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding natural logarithm of
    // the specified complex number
    // Using Log() function
    res_1 := cmplx.Log(1i)
    res_2 := cmplx.Log(-4 + 12i)
    res_3 := cmplx.Log(-3 - 9i)

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2:  %.1f", res_2)
    fmt.Printf("\nResult 3:  %.1f", res_3)
}
```

**输出:**

```go
Result 1: (0.0+1.6i)
Result 2:  (2.5+1.9i)
Result 3:  (2.2-1.9i)

```

**例 2:**

```go
// Golang program to illustrate how to find the
// natural logarithm of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(0, 2)
    cnumber_2 := complex(4, 6)

    // Finding natural logarithm
    cvalue_1 := cmplx.Log(cnumber_1)
    cvalue_2 := cmplx.Log(cnumber_2)

    // Sum of the given natural logarithm
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Printf("Natural logarithm 1: %.1f", cvalue_1)

    fmt.Println("\nComplex Number 2: ", cnumber_2)
    fmt.Printf("Natural logarithm 2: %.1f ", cvalue_2)
    fmt.Printf("\nSum : %.1f", res)

}
```

**输出:**

```go
Complex Number 1:  (0+2i)
Natural logarithm 1: (0.7+1.6i)
Complex Number 2:  (4+6i)
Natural logarithm 2: (2.0+1.0i) 
Sum : (2.7+2.6i)

```