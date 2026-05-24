# 求 Golang 中复数的反余弦

> 原文:[https://www . geesforgeks . org/golang/find-复数反余弦/](https://www.geeksforgeeks.org/finding-the-inverse-cosine-of-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。您可以借助*数学/cmplx 软件包*提供的 **Acos()函数**找到指定复数的反余弦。因此，您需要借助 import 关键字在程序中添加一个 math/cmplx 包来访问 Acos()函数。

**语法:**

```go
func Acos(x complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1 :**

```go
// Golang program to illustrate
// how to find inverse cosine of
// complex number
package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding inverse cosine of the
    // specified complex number
    // Using Acos() function
    res_1 := cmplx.Acos(3 + 5i)
    res_2 := cmplx.Acos(-4 + 8i)
    res_3 := cmplx.Acos(-8 - 7i)

    // Displaying the result
    fmt.Println("Result 1:", res_1)
    fmt.Println("Result 2:", res_2)
    fmt.Println("Result 3:", res_3)
}
```

**输出:**

```go
Result 1: (1.0367972572007265-2.4598315216234306i)
Result 2: (2.031957962047241-2.886039504947561i)
Result 3: (2.4205679446613617+3.0565545070216835i)

```

**例 2 :**

```go
// Golang program to illustrate how to find
// Inverse Cosine of Complex Number
package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(5, 7)
    cnumber_2 := complex(6, 9)

    // Finding inverse cosine
    cvalue_1 := cmplx.Acos(cnumber_1)
    cvalue_2 := cmplx.Acos(cnumber_2)

    // Sum of two inverse cosine values
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Println("Inverse Cosine 1: ", cvalue_1)

    fmt.Println("Complex Number 2: ", cnumber_2)
    fmt.Println("Inverse Cosine 2: ", cvalue_2)
    fmt.Println("Final sum: ", res)

}
```

**输出:**

```go
Complex Number 1:  (5+7i)
Inverse Cosine 1:  (0.9537320301189085-2.846288828208389i)
Complex Number 2:  (6+9i)
Inverse Cosine 2:  (0.9847612348751953-3.075060767946888i)
Final sum:  (1.9384932649941038-5.921349596155277i)

```