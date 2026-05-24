# 位。Golang 中的反向()函数示例

> 原文:[https://www . geesforgeks . org/bits-反向函数 in-golang-with-examples/](https://www.geeksforgeeks.org/bits-reverse-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。该包提供 **Reverse()函数**，用于查找 a 值的逆序，要访问 Reverse()函数，需要在 import 关键字的帮助下，在程序中添加一个数学/位包。

**语法:**

```go
func Reverse(a uint) uint
```

**参数:**该函数取 uint 类型的一个参数，即 a

**返回值:**该函数返回一个的值，其位的顺序相反。

**例 1:**

```go
// Golang program to illustrate bits.Reverse() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using Reverse() function
    a := bits.Reverse(5)
    fmt.Printf("Reverse order of %d: %b", 5, a)

}
```

**输出:**

```go
Reverse order of 5: 1010000000000000000000000000000000000000000000000000000000000000
```

**例 2:**

```go
// Golang program to illustrate bits.Reverse() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using Reverse() function
    a1 := bits.Reverse(23)
    fmt.Printf("Reverse(%b) := %b\n", 23, a1)

    a2 := bits.Reverse(13)
    fmt.Printf("Reverse(%b) := %b\n", 13, a2)

}
```

**输出:**

> 反向(10111):= 1110100000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000