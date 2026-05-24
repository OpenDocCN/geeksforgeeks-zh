# 求 Golang 中复数的双曲正弦

> 原文:[https://www . geeksforgeeks . org/find-the-双曲正弦复数 in-golang/](https://www.geeksforgeeks.org/finding-the-hyperbolic-sine-of-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。您可以借助 math/cmplx 包提供的 **Sinh()函数**找到指定复数的双曲正弦。因此，您需要借助 import 关键字在程序中添加一个 math/cmplx 包来访问 Sinh()函数。

**语法:**

```go
func Sinh(y complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate how to find the
// hyperbolic sine of the specified complex number
package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding hyperbolic sine of 
    // the specified complex number
    // Using Sinh() function
    res_1 := cmplx.Sinh(1 + 5i)
    res_2 := cmplx.Sinh(-2 + 8i)
    res_3 := cmplx.Sinh(-1 - 2i)

    // Displaying the result
    fmt.Println("Result 1:", res_1)
    fmt.Println("Result 2:", res_2)
    fmt.Println("Result 3:", res_3)
}
```

**输出:**

```go
Result 1: (0.33336013894799293-1.4796974784869428i)
Result 2: (0.5277083119608631+3.722159332384543i)
Result 3: (0.4890562590412937-1.4031192506220405i)

```

**例 2:**

```go
// Golang program to illustrate how to find the
// hyperbolic sine of the specified complex number
package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(0, 2)
    cnumber_2 := complex(4, 6)

    // Finding hyperbolic sine
    cvalue_1 := cmplx.Sinh(cnumber_1)
    cvalue_2 := cmplx.Sinh(cnumber_2)

    // Sum of two hyperbolic sine values
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Println("Hyperbolic sine 1: ", cvalue_1)

    fmt.Println("Complex Number 2: ", cnumber_2)
    fmt.Println("Hyperbolic sine 2: ", cvalue_2)
    fmt.Println("Sum : ", res)

}
```

**输出:**

```go
Complex Number 1:  (0+2i)
Hyperbolic sine 1:  (-0+0.9092974268256816i)
Complex Number 2:  (4+6i)
Hyperbolic sine 2:  (26.202967617830907-7.630343482807812i)
Sum :  (26.202967617830907-6.72104605598213i)

```