# 位。Golang 中的 ReverseBytes16()函数及示例

> 原文:[https://www . geesforgeks . org/bits-reverse byte 16-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-reversebytes16-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 **ReverseBytes16()函数**，该函数用于查找 a 值的逆序。要访问 ReverseBytes16()函数，您需要在 import 关键字的帮助下在程序中添加一个数学/位包。

**语法:**

```go
func ReverseBytes16(a uint16) uint16
```

**参数:**该函数取 uint16 类型的一个参数，即 a。

**返回值:**该函数返回一个的值，其位的顺序相反。

**例 1:**

```go
// Golang program to illustrate
// bits.ReverseBytes16() Function

package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding the reverse order of a
    // Using ReverseBytes16() function
    a := bits.ReverseBytes16(7)
    fmt.Printf("Reverse order of %d: %b", 7, a)

}
```

**输出:**

```go
Reverse order of 7: 11100000000
```

**例 2:**

```go
// Golang program to illustrate
// bits.ReverseBytes16() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding the reverse order of a
    // Using ReverseBytes16() function
    a1 := bits.ReverseBytes16(3)
    fmt.Printf("ReverseBytes16(%016b) := %b\n", 3, a1)

    a2 := bits.ReverseBytes16(7)
    fmt.Printf("ReverseBytes16(%016b) := %b\n", 7, a2)

}
```

**输出:**

```go
ReverseBytes16(0000000000000011) := 1100000000
ReverseBytes16(0000000000000111) := 11100000000

```