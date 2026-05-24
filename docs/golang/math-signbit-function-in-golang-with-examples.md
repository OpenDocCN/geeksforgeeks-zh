# 数学。Golang 中 Signbit()函数示例

> 原文:[https://www . geesforgeks . org/math-sign bit-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-signbit-function-in-golang-with-examples/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。您可以借助**数学包**提供的 **Signbit()功能**检查指定数字的符号是负还是负零。如果给定数字的符号是负数，那么这个函数将返回 true。否则，返回 false。因此，您需要在导入关键字的帮助下在程序中添加一个数学包来访问 Signbit()函数。

**语法:**

```go
func Signbit(x float64) bool
```

**例 1:**

```go
// Golang program to illustrate Signbit() Function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Using Signbit() function
    res_1 := math.Signbit(-6)
    res_2 := math.Signbit(54)
    res_3 := math.Signbit(math.Inf(-1))
    res_4 := math.Signbit(math.NaN())
    res_5 := math.Signbit(math.Pi)

    // Displaying the result
    fmt.Println("Result 1: ", res_1)
    fmt.Println("Result 2: ", res_2)
    fmt.Println("Result 3: ", res_3)
    fmt.Println("Result 4: ", res_4)
    fmt.Println("Result 5: ", res_5)

}
```

**输出:**

```go
Result 1:  true
Result 2:  false
Result 3:  true
Result 4:  false
Result 5:  false

```

**例 2:**

```go
// Golang program to illustrate Signbit() Function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Using Signbit() function
    nvalue := math.Signbit(-34)
    if nvalue == true {
        fmt.Println("Sign of the "+
          "given number is negative")
    } else {
        fmt.Println("Sign of the given "+
                "number is not negative")
    }

}
```

**输出:**

```go
Sign of the given number is negative
```