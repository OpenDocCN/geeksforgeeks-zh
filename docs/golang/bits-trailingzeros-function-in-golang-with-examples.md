# 位。Golang 中 TrailingZeros()函数示例

> 原文:[https://www . geesforgeks . org/bits-trailingeros-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-trailingzeros-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 TrailingZeros()函数，该函数用于查找中的尾随零位数，结果是 a == 0 的 UintSize。要访问 TrailingZeros()函数，您需要借助 import 关键字在程序中添加一个数学/位包。

**语法:**

```go
func TrailingZeros(a uint) int
```

**参数:**该函数取 uint 类型的一个参数，即 a

**返回值:**这个函数返回一个

**例 1:**

```go
// Golang program to illustrate
// bits.TrailingZeros() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using TrailingZeros() function
    a := bits.TrailingZeros(6)
    fmt.Printf("Total number of trailing"+
             " zero bits in %d: %d", 6, a)

}
```

**输出:**

```go
Total number of trailing zero bits in 6: 1
```

**例 2 :**

```go
// Golang program to illustrate
// bits.TrailingZeros() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using TrailingZeros() function
    a1 := bits.TrailingZeros(8)
    fmt.Printf("TrailingZeros(%b)) := %d\n", 8, a1)

    a2 := bits.TrailingZeros(13)
    fmt.Printf("TrailingZeros(%b) := %d\n", 13, a2)

}
```

**输出:**

```go
TrailingZeros(1000)) := 3
TrailingZeros(1101) := 0

```