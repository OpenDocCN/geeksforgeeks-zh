# 求 Golang 中复数的反正切

> 原文:[https://www . geesforgeks . org/golang 中复数的求逆切线/](https://www.geeksforgeeks.org/finding-the-inverse-tangent-of-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。您可以借助数学/cmplx 软件包提供的 **Atan()函数**找到指定复数的反正切。因此，您需要借助 import 关键字在程序中添加一个 math/cmplx 包来访问 Atan()函数。

**语法:**

```go
func Atan(x complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate how to find
// Inverse Tangent of Complex Number
package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding inverse tangent of the 
    // specified complex number
    // Using Atan() function
    res_1 := cmplx.Atan(3 + 5i)
    res_2 := cmplx.Atan(-4 + 8i)
    res_3 := cmplx.Atan(-8 - 7i)

    // Displaying the result
    fmt.Println("Result 1:", res_1)
    fmt.Println("Result 2:", res_2)
    fmt.Println("Result 3:", res_3)
}
```

**输出:**

```go
Result 1: (1.4808695768986575+0.14694666622552977i)
Result 2: (-1.5203354344612496+0.10008092715193644i)
Result 3: (-1.4998477994928145-0.06171501948288145i)

```

**例 2:**

```go
// Golang program to illustrate how to find
// Inverse Tangent of Complex Number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(5, 7)
    cnumber_2 := complex(6, 9)

    // Finding inverse tangent
    cvalue_1 := cmplx.Atan(cnumber_1)
    cvalue_2 := cmplx.Atan(cnumber_2)

    // Sum of two inverse tangent values
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Println("Inverse tangent 1: ", cvalue_1)

    fmt.Println("Complex Number 2: ", cnumber_2)
    fmt.Println("Inverse tangent 2: ", cvalue_2)
    fmt.Println("Final sum: ", res)

}
```

**输出:**

```go
Complex Number 1:  (5+7i)
Inverse tangent 1:  (1.502726846368326+0.09444062638970716i)
Complex Number 2:  (6+9i)
Inverse tangent 2:  (1.5192555225335465+0.07687117493699018i)
Final sum:  (3.0219823689018726+0.17131180132669732i)

```