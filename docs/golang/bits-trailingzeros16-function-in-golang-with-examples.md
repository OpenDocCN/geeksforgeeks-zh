# 位。TrailingZeros16()在 Golang 中的功能举例

> 原文:[https://www . geesforgeks . org/bits-trailingeros 16-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-trailingzeros16-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了**trailingeros 16()函数**，该函数用于查找 a 中的尾随零位数，对于 a == 0，结果是 16。要访问 TrailingZeros16()函数，您需要借助 import 关键字在程序中添加一个数学/位包。

**语法:**

```go
func TrailingZeros16(a uint16) int
```

**参数:**该函数取 uint16 类型的一个参数，即 a。

**返回值:**这个函数返回一个

**例 1:**

```go
// Golang program to illustrate 
// bits.TrailingZeros16() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using TrailingZeros16() function
    a := bits.TrailingZeros16(15)
    fmt.Printf("Total number of trailing"+
            " zero bits in %d: %d", 15, a)

}
```

**输出:**

```go
Total number of trailing zero bits in 15: 0
```

**例 2:**

```go
// Golang program to illustrate
// bits.TrailingZeros16() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using TrailingZeros16() function
    a1 := bits.TrailingZeros16(8)
    fmt.Printf("TrailingZeros16(%016b)) := %d\n", 8, a1)

    a2 := bits.TrailingZeros16(13)
    fmt.Printf("TrailingZeros16(%016b) := %d\n", 13, a2)

}
```

**输出:**

```go
TrailingZeros16(0000000000001000)) := 3
TrailingZeros16(0000000000001101) := 0

```