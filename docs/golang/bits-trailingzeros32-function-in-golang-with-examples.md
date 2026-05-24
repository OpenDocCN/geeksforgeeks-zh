# 位。TrailingZeros32()在 Golang 中的功能举例

> 原文:[https://www . geesforgeks . org/bits-trailingeros 32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-trailingzeros32-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了**trailingeros 32()函数**，用于查找 a 中的尾随零位数，a == 0 的结果是 32。要访问 TrailingZeros32()函数，您需要借助 import 关键字在程序中添加一个数学/位包。

**语法:**

```go
func TrailingZeros32(a uint32) int
```

**参数:**该函数取 uint32 类型的一个参数，即 a。

**返回值:**这个函数返回一个

**例 1:**

```go
// Golang program to illustrate 
// bits.TrailingZeros32() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using TrailingZeros32() function
    a := bits.TrailingZeros32(15)
    fmt.Printf("Total number of trailing "+
             "zero bits in %d: %d", 15, a)

}
```

**输出:**

```go
Total number of trailing zero bits in 15: 0
```

**例 2 :**

```go
// Golang program to illustrate
// bits.TrailingZeros32() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using TrailingZeros32() function
    a1 := bits.TrailingZeros32(8)
    fmt.Printf("TrailingZeros32(%032b)) := %d\n", 8, a1)

    a2 := bits.TrailingZeros32(13)
    fmt.Printf("TrailingZeros32(%032b) := %d\n", 13, a2)

}
```

**输出:**

```go
TrailingZeros32(00000000000000000000000000001000)) := 3
TrailingZeros32(00000000000000000000000000001101) := 0

```