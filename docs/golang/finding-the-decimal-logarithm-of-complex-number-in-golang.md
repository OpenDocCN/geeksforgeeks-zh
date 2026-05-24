# 求 Golang 中复数的十进制对数

> 原文:[https://www . geesforgeks . org/golang 中复数的十进制对数查找/](https://www.geeksforgeeks.org/finding-the-decimal-logarithm-of-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。允许你借助 math/cmplx 包提供的 **Log10()函数**求指定复数的十进制对数。因此，您需要在 import 关键字的帮助下在程序中添加一个 math/cmplx 包来访问 Log10()函数。

**语法:**

```go
func Log10(y complex128) complex128
```

**例 1:**

```go
// Golang program to illustrate how to find the
// decimal logarithm of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding decimal logarithm of
    // the specified complex number
    // Using Log10() function
    res_1 := cmplx.Log10(1i)
    res_2 := cmplx.Log10(-4 + 12i)
    res_3 := cmplx.Log10(-3 - 9i)

    // Displaying the result
    fmt.Printf("Result 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
}
```

**输出:**

```go
Result 1: (0.0+0.7i)
Result 2: (1.1+0.8i)
Result 3: (1.0-0.8i)

```

**例 2:**

```go
// Golang program to illustrate how to find the
// decimal logarithm of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(0, 2)
    cnumber_2 := complex(4, 6)

    // Finding decimal logarithm
    cvalue_1 := cmplx.Log10(cnumber_1)
    cvalue_2 := cmplx.Log10(cnumber_2)

    // Sum of the given values
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Printf("Decimal logarithm 1: %.1f", cvalue_1)

    fmt.Println("\nComplex Number 2: ", cnumber_2)
    fmt.Printf("Decimal logarithm 2: %.1f ", cvalue_2)
    fmt.Printf("\nSum : %.1f", res)

}
```

**输出:**

```go
Complex Number 1:  (0+2i)
Decimal logarithm 1: (0.3+0.7i)
Complex Number 2:  (4+6i)
Decimal logarithm 2: (0.9+0.4i) 
Sum : (1.2+1.1i)

```