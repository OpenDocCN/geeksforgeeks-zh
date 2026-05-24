# 求 Golang 中复数的反正弦

> 原文:[https://www . geeksforgeeks . org/golang 中复数正弦的求逆运算/](https://www.geeksforgeeks.org/finding-the-inverse-sine-of-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。您可以借助数学/cmplx 软件包提供的 **Asin()函数**找到指定复数的反正弦。因此，您需要借助 import 关键字在程序中添加一个 math/cmplx 包来访问 Asin()函数。

**语法:**

```go
func Asin(x complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate how to find
// the Inverse Sine of Complex Number
package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding inverse sine of the
    // specified complex number
    // Using Asin() function
    res_1 := cmplx.Asin(3 + 5i)
    res_2 := cmplx.Asin(-4 + 8i)
    res_3 := cmplx.Asin(-8 - 7i)

    // Displaying the result
    fmt.Println("Result 1:", res_1)
    fmt.Println("Result 2:", res_2)
    fmt.Println("Result 3:", res_3)
}
```

**输出:**

```go
Result 1: (0.5339990695941702+2.4598315216234306i)
Result 2: (-0.4611616352523445+2.886039504947561i)
Result 3: (-0.849771617866465-3.0565545070216835i)

```

**例 2:**

```go
// Golang program to illustrate how to find
// the Inverse Sine of Complex Number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(5, 7)
    cnumber_2 := complex(6, 9)

    // Finding inverse sine
    cvalue_1 := cmplx.Asin(cnumber_1)
    cvalue_2 := cmplx.Asin(cnumber_2)

    // Sum of two inverse sine values
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Println("Inverse sine 1: ", cvalue_1)

    fmt.Println("Complex Number 2: ", cnumber_2)
    fmt.Println("Inverse sine 2: ", cvalue_2)
    fmt.Println("Final sum: ", res)

}
```

**输出:**

```go
Complex Number 1:  (5+7i)
Inverse sine 1:  (0.617064296675988+2.846288828208389i)
Complex Number 2:  (6+9i)
Inverse sine 2:  (0.5860350919197013+3.075060767946888i)
Final sum:  (1.2030993885956893+5.921349596155277i)

```