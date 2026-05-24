# 位。Golang 中的 ReverseBytes32()函数示例

> 原文:[https://www . geesforgeks . org/bits-reversebytes32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-reversebytes32-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 **ReverseBytes32()函数**，该函数用于查找 a 值的逆序。要访问 ReverseBytes32()函数，您需要借助 import 关键字在程序中添加一个数学/位包。

**语法:**

```go
func ReverseBytes32(a uint32) uint32
```

**参数:**该函数取 uint32 类型的一个参数，即 a。

**返回值:**该函数返回一个的值，其位的顺序相反。

**例 1:**

```go
// Golang program to illustrate 
// bits.ReverseBytes32() Function

package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding the reverse order of a
    // Using ReverseBytes32() function
    a := bits.ReverseBytes32(7)
    fmt.Printf("Reverse order of %d: %b", 7, a)

}
```

**输出:**

```go
Reverse order of 7: 111000000000000000000000000
```

**例 2:**

```go
// Golang program to illustrate
// bits.ReverseBytes32() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding the reverse order of a
    // Using ReverseBytes32() function
    a1 := bits.ReverseBytes32(3)
    fmt.Printf("ReverseBytes32(%032b) := %b\n", 3, a1)

    a2 := bits.ReverseBytes32(9)
    fmt.Printf("ReverseBytes32(%032b) := %b\n", 9, a2)

}
```

**输出:**

```go
ReverseBytes32(00000000000000000000000000000011) := 11000000000000000000000000
ReverseBytes32(00000000000000000000000000001001) := 1001000000000000000000000000

```