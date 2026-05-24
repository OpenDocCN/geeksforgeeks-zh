# 求高朗复数的反双曲正切值

> 原文:[https://www . geeksforgeeks . org/golang 中求复数的反双曲正切/](https://www.geeksforgeeks.org/finding-the-inverse-hyperbolic-tangent-of-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。您可以借助 math/cmplx 包提供的 **Atanh()函数**找到指定复数的反双曲正切。因此，您需要在 import 关键字的帮助下在程序中添加一个 math/cmplx 包来访问 Atanh()函数。

**语法:**

```go
func Atanh(x complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate how to find the
// Inverse Hyperbolic Tangent of Complex Number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding the inverse hyperbolic tangent 
    // of the specified complex number
    // Using Atanh() function
    res_1 := cmplx.Atanh(2 + 5i)
    res_2 := cmplx.Atanh(-9 + 8i)
    res_3 := cmplx.Atanh(-5 - 7i)

    // Displaying the result
    fmt.Println("Result 1:", res_1)
    fmt.Println("Result 2:", res_2)
    fmt.Println("Result 3:", res_3)
}
```

**输出:**

```go
Result 1: (0.06706599664866984+1.3992843565845448i)
Result 2: (-0.0619590409761453+1.5154677162079488i)
Result 3: (-0.06706599664866986-1.4760562478543229i)

```

**例 2 :**

```go
// Golang program to illustrate how to find
// Inverse Hyperbolic Tangent of Complex Number
package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(5, 7)
    cnumber_2 := complex(6, 9)

    // Finding inverse hyperbolic tangent
    cvalue_1 := cmplx.Atanh(cnumber_1)
    cvalue_2 := cmplx.Atanh(cnumber_2)

    // Sum of two inverse hyperbolic tangent values
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Println("Inverse hyperbolic tangent 1: ", cvalue_1)

    fmt.Println("Complex Number 2: ", cnumber_2)
    fmt.Println("Inverse hyperbolic tangent 2: ", cvalue_2)
    fmt.Println("Sum of inverse hyperbolic tangents : ", res)

}
```

**输出:**

```go
Complex Number 1:  (5+7i)
Inverse hyperbolic tangent 1:  (0.06706599664866984+1.4760562478543229i)
Complex Number 2:  (6+9i)
Inverse hyperbolic tangent 2:  (0.051023839085878805+1.4938239945657217i)
Sum of inverse hyperbolic tangents :  (0.11808983573454865+2.969880242420045i)

```