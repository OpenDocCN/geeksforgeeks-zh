# 求戈朗复数的余切

> 原文:[https://www . geesforgeks . org/find-复数余切在 golang/](https://www.geeksforgeeks.org/finding-the-cotangent-of-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。您可以借助数学/cmplx 软件包提供的 **Cot()函数**找到指定复数的余切。因此，您需要借助 import 关键字在程序中添加一个 math/cmplx 包来访问 Cot()函数。

**语法:**

```go
func Cot(y complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate how to find the
// cotangent value of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding cotangent of the
    // specified complex number
    // Using Cot() function
    res_1 := cmplx.Cot(2 + 5i)
    res_2 := cmplx.Cot(-1 + 8i)
    res_3 := cmplx.Cot(-1 - 7i)

    // Displaying the result
    fmt.Println("Result 1:", res_1)
    fmt.Println("Result 2:", res_2)
    fmt.Println("Result 3:", res_3)
}
```

**输出:**

```go
Result 1: (-6.871348192386196e-05-0.9999406486514081i)
Result 2: (-2.0465587043065668e-07-0.9999999063376698i)
Result 3: (-1.5122128026576863e-06+0.9999993079230043i)

```

**例 2:**

```go
// Golang program to illustrate how to find the
// cotangent value of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(1, 2)
    cnumber_2 := complex(3, 6)

    // Finding cotangent
    cvalue_1 := cmplx.Cot(cnumber_1)
    cvalue_2 := cmplx.Cot(cnumber_2)

    // Sum of two cotangent values
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Println("Cotangent 1: ", cvalue_1)

    fmt.Println("Complex Number 2: ", cnumber_2)
    fmt.Println("Cotangent 2: ", cvalue_2)
    fmt.Println("Sum : ", res)

}
```

**输出:**

```go
Complex Number 1:  (1+2i)
Cotangent 1:  (0.03279775553375259-0.984329226458191i)
Complex Number 2:  (3+6i)
Cotangent 2:  (-3.433616824537947e-06-1.0000117990439865i)
Sum :  (0.03279432191692805-1.9843410255021774i)

```