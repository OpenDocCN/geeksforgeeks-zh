# 位。Golang 中 RotateLeft16()函数示例

> 原文:[https://www . geesforgeks . org/bits-rotateleft16-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-rotateleft16-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 **RotateLeft16()函数**，用来将左边旋转(k mod 16)位，将右边旋转 k 位，你需要调用 RotateLeft16(a，-k)。要访问 RotateLeft16()函数，您需要在 import 关键字的帮助下在程序中添加一个数学/位包。

**语法:**

```go
func RotateLeft16(a uint16, k int) uint16
```

**参数:**该函数取两个参数，即 uint16 类型的 a 和 int 类型的 k。

**返回值:**该函数返回 uint16 类型的旋转(左或右)值。

**例 1:**

```go
// Golang program to illustrate bits.RotateLeft16() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using RotateLeft16() function
    var a uint16 = 6
    b := bits.RotateLeft16(a, 5)
    fmt.Printf("Original: %b", a)
    fmt.Printf("\nAfter Rotation(Left): %b", b)

}
```

**输出:**

```go
Original: 110
After Rotation(Left): 11000000

```

**例 2:**

```go
// Golang program to illustrate bits.RotateLeft16() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using RotateLeft16() function
    var a uint16 = 5
    b := bits.RotateLeft16(a, -1)
    fmt.Printf("Original: %b", a)
    fmt.Printf("\nAfter Rotation(Right): %b", b)

}
```

**输出:**

```go
Original: 101
After Rotation(Right): 1000000000000010

```