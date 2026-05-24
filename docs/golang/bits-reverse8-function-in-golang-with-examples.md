# 位。Golang 中的 Reverse8()函数示例

> 原文:[https://www . geesforgeks . org/bits-reverse 8-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-reverse8-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 **Reverse8()函数**，用来查找 a 值的逆序，要访问 Reverse8()函数，需要在 import 关键字的帮助下，在程序中添加一个数学/位包。

**语法:**

```go
 func Reverse8(a uint8) uint8
```

**参数:**该函数取 uint8 类型的一个参数，即 a。

**返回值:**该函数返回一个的值，其位的顺序相反。

**例 1:**

```go
// Golang program to illustrate bits.Reverse8() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using Reverse8() function
    a := bits.Reverse8(5)
    fmt.Printf("Reverse order of %d: %b", 5, a)

}
```

**输出:**

```go
Reverse order of 5: 10100000
```

**例 2 :**

```go
// Golang program to illustrate bits.Reverse8() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using Reverse8() function
    a1 := bits.Reverse8(9)
    fmt.Printf("Reverse8(%08b) := %b\n", 9, a1)

    a2 := bits.Reverse8(13)
    fmt.Printf("Reverse8(%08b) := %b\n", 13, a2)

}
```

**输出:**

```go
Reverse8(00001001) := 10010000
Reverse8(00001101) := 10110000

```