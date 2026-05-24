# 位。Golang 中 TrailingZeros8()函数示例

> 原文:[https://www . geesforgeks . org/bits-trailing zero 8-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-trailingzeros8-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了**trailingeros 8()函数**，用来求 a 中尾随零位数，a == 0 时结果为 8。要访问 TrailingZeros8()函数，您需要借助 import 关键字在程序中添加一个数学/位包。

**语法:**

```go
func TrailingZeros8(a uint8) int
```

**参数:**该函数取 uint8 类型的一个参数，即 a。

**返回值:**这个函数返回一个

**例 1 :**

```go
// Golang program to illustrate
// bits.TrailingZeros8() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using TrailingZeros8() function
    a := bits.TrailingZeros8(6)
    fmt.Printf("Total number of trailing "+
        "zero bits in %d: %d", 6, a)

}
```

**输出:**

```go
Total number of trailing zero bits in 6: 1
```

**例 2 :**

```go
// Golang program to illustrate
// bits.TrailingZeros8() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using TrailingZeros8() function
    a1 := bits.TrailingZeros8(8)
    fmt.Printf("TrailingZeros8(%08b)) := %d\n", 8, a1)

    a2 := bits.TrailingZeros8(13)
    fmt.Printf("TrailingZeros8(%08b) := %d\n", 13, a2)

}
```

**输出:**

```go
TrailingZeros8(00001000)) := 3
TrailingZeros8(00001101) := 0

```