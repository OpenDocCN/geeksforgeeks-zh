# 位。Div64()在 Golang 中的作用举例

> 原文:[https://www . geesforgeks . org/bits-div 64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-div64-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 **Div64()函数**，用来求(a，b)除以 c 的商和余数，即 q = (a，b)/c，r = (a，b)%c，被除数位的上半部分在参数 a，下半部分在参数 b，如果 c == 0(被零除)或者 c < = a(商溢出)，这个函数就会死机。要访问 Div64()函数，您需要借助 import 关键字在程序中添加一个数学/位包。

**语法:**

```go
func Div64(a, b, c uint64) (q, r uint64)
```

**参数:**该函数取 uint64 类型的三个参数，即 a、b、c。

**返回值:**这个函数返回 uint64 类型的两个值，即 q 和 r，这里 q 称为商，r 称为余数。

**例 1:**

```go
// Golang program to illustrate bits.Div64() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding quotient and remainder
    // Using Div64() function
    q, r := bits.Div64(10, 12, 11)
    fmt.Println("Quotient:", q)
    fmt.Println("Remainder:", r)

}
```

**输出:**

```go
Quotient: 16769767339735956015
Remainder: 7

```

**例 2:**

```go
// Golang program to illustrate bits.Div64() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding quotient and remainder
    // Using Div64() function
    var a, b, c uint64 = 3, 10, 5
    q, r := bits.Div64(a, b, c)
    fmt.Println("Number 1:", a)
    fmt.Println("Number 2:", b)
    fmt.Println("Number 3:", c)
    fmt.Println("Quotient:", q)
    fmt.Println("Remainder:", r)

}
```

**输出:**

```go
Number 1: 3
Number 2: 10
Number 3: 5
Quotient: 11068046444225730971
Remainder: 3

```