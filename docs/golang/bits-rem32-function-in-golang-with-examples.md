# 位。Rem32()在 Golang 中的作用举例

> 原文:[https://www . geesforgeks . org/bits-rem 32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-rem32-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 **Rem32()函数**，用来求(h，l)除以 a 的余数，如果 a == 0(除零)这个函数会死机，如果商溢出也不会死机。要访问 Rem32()函数，您需要借助 import 关键字在程序中添加一个数学/位包。

**语法:**

```go
func Rem32(h, l, a uint32) uint32
```

**参数:**该函数取 uint32 类型的三个参数，即 h、l 和 a。

**返回值:**这个函数返回(h，l)除以 a 的余数

**例 1:**

```go
// Golang program to illustrate bits.Rem32() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding the remainder
    // Using Rem32() function
    var h, l, a uint32 = 3, 5, 2
    r := bits.Rem32(h, l, a)
    fmt.Println("Number 1:", h)
    fmt.Println("Number 2:", l)
    fmt.Println("Number 3:", a)
    fmt.Println("Remainder:", r)

}
```

**输出:**

```go
Number 1: 3
Number 2: 5
Number 3: 2
Remainder: 1

```

**例 2:**

```go
// Golang program to illustrate bits.Rem32() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding remainder
    // Using Rem32() function
    r := bits.Rem32(8, 9, 3)
    fmt.Println("Remainder:", r)

}
```

**输出:**

```go
Remainder: 2
```