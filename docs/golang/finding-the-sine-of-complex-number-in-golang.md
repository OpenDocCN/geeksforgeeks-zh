# 求 Golang 中复数的正弦值

> 原文:[https://www . geesforgeks . org/finding-the-sine-of-complex-number-in-golang/](https://www.geeksforgeeks.org/finding-the-sine-of-complex-number-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。您可以借助数学/cmplx 软件包提供的 **Sin()函数**找到指定复数的正弦值。因此，您需要借助 import 关键字在程序中添加一个 math/cmplx 包来访问 Sin()函数。

**语法:**

```go
func Sin(y complex128) complex128
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate how to find
// the sine value of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Finding sine of the 
    // specified complex number
    // Using Sin() function
    res_1 := cmplx.Sin(2 + 5i)
    res_2 := cmplx.Sin(-1 + 8i)
    res_3 := cmplx.Sin(-1 - 7i)

    // Displaying the result
    fmt.Println("Result 1:", res_1)
    fmt.Println("Result 2:", res_2)
    fmt.Println("Result 3:", res_3)
}
```

**输出:**

```go
Result 1: (67.47891523845587-30.879431343588244i)
Result 2: (-1254.1949676545178+805.3091464217314i)
Result 3: (-461.3928755590023-296.25646574921427i)

```

**例 2 :**

```go
// Golang program to illustrate how to find
// the sine value of the given complex number

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    cnumber_1 := complex(1, 2)
    cnumber_2 := complex(3, 6)

    // Finding sine
    cvalue_1 := cmplx.Sin(cnumber_1)
    cvalue_2 := cmplx.Sin(cnumber_2)

    // Sum of two sine values
    res := cvalue_1 + cvalue_2

    // Displaying results
    fmt.Println("Complex Number 1: ", cnumber_1)
    fmt.Println("Sine 1: ", cvalue_1)

    fmt.Println("Complex Number 2: ", cnumber_2)
    fmt.Println("Sine 2: ", cvalue_2)
    fmt.Println("Sum : ", res)

}
```

**输出:**

```go
Complex Number 1:  (1+2i)
Sine 1:  (3.165778513216168+1.9596010414216063i)
Complex Number 2:  (3+6i)
Sine 2:  (28.466112195402218-199.69451226216125i)
Sum :  (31.631890708618386-197.73491122073966i)

```