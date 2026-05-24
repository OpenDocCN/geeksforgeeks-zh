# 求 Golang 中复数的双曲余弦

> 原文:[https://www . geeksforgeeks . org/find-the-双曲线余弦复数 in-golang/](https://www.geeksforgeeks.org/finding-the-hyperbolic-cosine-of-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。您可以借助数学/cmplx 包提供的 **Cosh()函数**找到指定复数的双曲余弦。因此，您需要借助 import 关键字在程序中添加一个 math/cmplx 包来访问 Cosh()函数。

**语法:**

```go
func Cosh(y complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1 :**

```go
// Golang program to illustrate how to find the
// hyperbolic cosine of the specified complex
// number
package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding hyperbolic cosine of 
    // the specified complex number
    // Using Cosh() function
    res_1 := cmplx.Cosh(1 + 5i)
    res_2 := cmplx.Cosh(-2 + 8i)
    res_3 := cmplx.Cosh(-1 - 2i)

    // Displaying the result
    fmt.Println("Result 1:", res_1)
    fmt.Println("Result 2:", res_2)
    fmt.Println("Result 3:", res_3)
}
```

**输出:**

```go
Result 1: (0.43771362521767465-1.1269289521981367i)
Result 2: (-0.5473996002472885-3.5882642538552894i)
Result 3: (-0.64214812471552+1.068607421382778i)

```

**例 2 :**

```go
// Golang program to illustrate how to find the
// hyperbolic cosine of the specified complex
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

    // Finding hyperbolic cosine
    cvalue_1 := cmplx.Cosh(cnumber_1)
    cvalue_2 := cmplx.Cosh(cnumber_2)

    // Sum of two hyperbolic cosine values
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Println("Hyperbolic cosine 1: ", cvalue_1)

    fmt.Println("Complex Number 2: ", cnumber_2)
    fmt.Println("Hyperbolic cosine 2: ", cvalue_2)
    fmt.Println("Sum : ", res)

}
```

**输出:**

```go
Complex Number 1:  (0+2i)
Hyperbolic cosine 1:  (-0.4161468365471424+0i)
Complex Number 2:  (4+6i)
Hyperbolic cosine 2:  (26.220553750072888-7.625225809442885i)
Sum :  (25.804406913525746-7.625225809442885i)

```