# 求 Golang 中复数的反双曲余弦

> 原文:[https://www . geeksforgeeks . org/find-the-reverse-双曲线余弦复数 in-golang/](https://www.geeksforgeeks.org/finding-the-inverse-hyperbolic-cosine-of-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。允许你借助 math/cmplx 包提供的 **Acosh()函数**求指定复数的反双曲余弦。因此，您需要在 import 关键字的帮助下在程序中添加一个 math/cmplx 包来访问 Acosh()函数。

**语法:**

```go
func Acosh(x complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate how to find the
// Inverse Hyperbolic Cosine of Complex Number
package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding inverse hyperbolic cosine
    // of the specified complex number
    // Using Acosh() function
    res_1 := cmplx.Acosh(2 + 5i)
    res_2 := cmplx.Acosh(-9 + 8i)
    res_3 := cmplx.Acosh(-5 - 7i)

    // Displaying the result
    fmt.Println("Result 1:", res_1)
    fmt.Println("Result 2:", res_2)
    fmt.Println("Result 3:", res_3)
}
```

**输出:**

```go
Result 1: (2.3830308809003298+1.1961255219693694i)
Result 2: (3.181316253686062+2.4132370433090795i)
Result 3: (2.8462888282083862-2.18786062347089i)

```

**例 2 :**

```go
// Golang program to illustrate how to find the
// Inverse Hyperbolic Cosine of Complex Number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(2, 3)
    cnumber_2 := complex(6, 8)

    // Finding inverse hyperbolic cosine
    cvalue_1 := cmplx.Acosh(cnumber_1)
    cvalue_2 := cmplx.Acosh(cnumber_2)

    // Sum of two inverse hyperbolic cosine values
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Println("Inverse hyperbolic cosine 1: ", cvalue_1)

    fmt.Println("Complex Number 2: ", cnumber_2)
    fmt.Println("Inverse hyperbolic cosine 2: ", cvalue_2)
    fmt.Println("Sum of inverse hyperbolic cosines : ", res)

}
```

**输出:**

```go
Complex Number 1:  (2+3i)
Inverse hyperbolic cosine 1:  (1.9833870299165355+1.0001435424737974i)
Complex Number 2:  (6+8i)
Inverse hyperbolic cosine 2:  (2.9964401392355113+0.9296901439918359i)
Sum of inverse hyperbolic cosines :  (4.979827169152047+1.9298336864656334i)

```