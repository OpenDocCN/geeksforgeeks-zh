# 求高朗复数的正切值

> 原文:[https://www . geeksforgeeks . org/golang 中求复数正切/](https://www.geeksforgeeks.org/finding-the-tangent-of-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。借助数学/cmplx 包提供的 **Tan()函数**，可以求出指定复数的正切值。因此，您需要借助 import 关键字在程序中添加一个 math/cmplx 包来访问 Tan()函数。

**语法:**

```go
func Tan(y complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate how to find
// the tangent value of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding Tangent of the 
    // specified complex number
    // Using Tan() function
    res_1 := cmplx.Tan(2 + 5i)
    res_2 := cmplx.Tan(-1 + 8i)
    res_3 := cmplx.Tan(-1 - 7i)

    // Displaying the result
    fmt.Println("Result 1:", res_1)
    fmt.Println("Result 2:", res_2)
    fmt.Println("Result 3:", res_3)
}
```

**输出:**

```go
Result 1: (-6.872163880119275e-05+1.000059350149i)
Result 2: (-2.04655908767745e-07+1.0000000936622975i)
Result 3: (-1.5122148957917884e-06-1.0000006920751883i)

```

**例 2 :**

```go
// Golang program to illustrate how to find
// the tangent value of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(1, 2)
    cnumber_2 := complex(3, 6)

    // Finding tangent
    cvalue_1 := cmplx.Tan(cnumber_1)
    cvalue_2 := cmplx.Tan(cnumber_2)

    // Sum of two tangent values
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Println("Tangent 1: ", cvalue_1)

    fmt.Println("Complex Number 2: ", cnumber_2)
    fmt.Println("Tangent 2: ", cvalue_2)
    fmt.Println("Sum : ", res)

}
```

**输出:**

```go
Complex Number 1:  (1+2i)
Tangent 1:  (0.033812826079896684+1.0147936161466335i)
Complex Number 2:  (3+6i)
Tangent 2:  (-3.433535799139611e-06+0.9999882010834397i)
Sum :  (0.033809392544097545+2.014781817230073i)

```