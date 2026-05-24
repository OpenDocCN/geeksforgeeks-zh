# 位。Golang 中的 ReverseBytes()函数示例

> 原文:[https://www . geesforgeks . org/bits-reverse bytes-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-reversebytes-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 ReverseBytes()函数，用来查找 a 值的逆序，要访问 **ReverseBytes()函数**，需要在 import 关键字的帮助下，在程序中添加一个数学/位包。

**语法:**

```go
func ReverseBytes(a uint) uint
```

**参数:**该函数取 uint 类型的一个参数，即 a

**返回值:**该函数返回一个的值，其位的顺序相反。

**例 1:**

```go
// Golang program to illustrate 
// bits.ReverseBytes() Function

package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding the reverse order of a
    // Using ReverseBytes() function
    a := bits.ReverseBytes(7)
    fmt.Printf("Reverse order of %d: %b", 7, a)

}
```

**输出:**

```go
Reverse order of 7: 11100000000000000000000000000000000000000000000000000000000
```

**例 2:**

```go
// Golang program to illustrate
// bits.ReverseBytes() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding the reverse order of a
    // Using ReverseBytes() function
    a1 := bits.ReverseBytes(3)
    fmt.Printf("ReverseBytes(%b) := %b\n", 3, a1)

    a2 := bits.ReverseBytes(7)
    fmt.Printf("ReverseBytes(%b) := %b\n", 7, a2)

}
```

**输出:**

```go
ReverseBytes(11) := 1100000000000000000000000000000000000000000000000000000000
ReverseBytes(111) := 11100000000000000000000000000000000000000000000000000000000

```