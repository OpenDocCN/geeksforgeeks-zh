# 求 Golang 中复数的余弦

> 原文:[https://www . geesforgeks . org/golang 中复数余弦的求法/](https://www.geeksforgeeks.org/finding-the-cosine-of-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。您可以借助数学/cmplx 包提供的 **Cos()函数**找到指定复数的余弦。因此，您需要借助 import 关键字在程序中添加一个 math/cmplx 包来访问 Cos()函数。

**语法:**

```go
func Cos(y complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate how to find
// the cosine value of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding Cosine of the 
    // specified complex number
    // Using Cos() function
    res_1 := cmplx.Cos(2 + 5i)
    res_2 := cmplx.Cos(-1 + 8i)
    res_3 := cmplx.Cos(-1 - 7i)

    // Displaying the result
    fmt.Println("Result 1:", res_1)
    fmt.Println("Result 2:", res_2)
    fmt.Println("Result 3:", res_3)
}
```

**输出:**

```go
Result 1: (-30.88223531891674-67.47278844058751i)
Result 2: (805.3093276729627+1254.19468537245i)
Result 3: (296.2569584411429-461.3921082367867i)

```

**例 2:**

```go
// Golang program to illustrate how to find
// the cosine value of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(1, 2)
    cnumber_2 := complex(3, 6)

    // Finding cosine
    cvalue_1 := cmplx.Cos(cnumber_1)
    cvalue_2 := cmplx.Cos(cnumber_2)

    // Sum of two cosine values
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Println("Cosine 1: ", cvalue_1)

    fmt.Println("Complex Number 2: ", cnumber_2)
    fmt.Println("Cosine 2: ", cvalue_2)
    fmt.Println("Sum : ", res)

}
```

**输出:**

```go
Complex Number 1:  (1+2i)
Cosine 1:  (2.0327230070196656-3.0518977991518i)
Complex Number 2:  (3+6i)
Cosine 2:  (-199.6969662082171-28.465762393875067i)
Sum :  (-197.66424320119745-31.517660193026867i)

```