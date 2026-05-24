# 位。Golang 中的 Reverse32()函数示例

> 原文:[https://www . geesforgeks . org/bits-reverse 32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-reverse32-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 **Reverse32()函数**，该函数用于查找 a 值的逆序。要访问 Reverse32()函数，您需要借助 import 关键字在程序中添加一个数学/位包。

**语法:**

```go
func Reverse32(a uint32) uint32
```

**参数:**该函数取 uint32 类型的一个参数，即 a。

**返回值:**该函数返回一个的值，其位的顺序相反。

**例 1:**

```go
// Golang program to illustrate bits.Reverse32() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using Reverse32() function
    a := bits.Reverse32(5)
    fmt.Printf("Reverse order of %d: %b", 5, a)

}
```

**输出:**

```go
Reverse order of 5: 10100000000000000000000000000000
```

**例 2 :**

```go
// Golang program to illustrate bits.Reverse32() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using Reverse32() function
    a1 := bits.Reverse32(9)
    fmt.Printf("Reverse32(%032b) := %b\n", 9, a1)

    a2 := bits.Reverse32(13)
    fmt.Printf("Reverse32(%032b) := %b\n", 13, a2)

}
```

**输出:**

> 反转 32(0000000000000000000000000000000001):= 100100000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000