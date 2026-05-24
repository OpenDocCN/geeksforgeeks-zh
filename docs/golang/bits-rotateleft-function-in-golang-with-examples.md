# 位。Golang 中的 RotateLeft()函数示例

> 原文:[https://www . geesforgeks . org/bits-rotateleft-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-rotateleft-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 **RotateLeft()函数**，该函数用于向左旋转(k mod UintSize)位，向右旋转 k 位，您需要调用 RotateLeft(a，-k)。要访问 RotateLeft()函数，您需要借助 import 关键字在程序中添加一个数学/位包。

**语法:**

```go
func RotateLeft(a uint, k int) uint
```

**参数:**该函数取两个参数，即 uint 类型的 a 和 int 类型的 k。

**返回值:**该函数返回 uint 类型的旋转(左或右)值。

**例 1:**

```go
// Golang program to illustrate bits.RotateLeft() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using RotateLeft() function
    var a uint = 5
    b := bits.RotateLeft(a, 1)
    fmt.Printf("Original: %b", a)
    fmt.Printf("\nAfter Rotation(Left): %b", b)

}
```

**输出:**

```go
Original: 101
After Rotation(Left): 1010

```

**例 2:**

```go
// Golang program to illustrate bits.RotateLeft() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using RotateLeft() function
    var a uint = 5
    b := bits.RotateLeft(a, -1)
    fmt.Printf("Original: %b", a)
    fmt.Printf("\nAfter Rotation(Right): %b", b)

}
```

**输出:**

> 原文:101
> 旋转后(右):10000000000000000000000000000000000000000000000000000000000000000000010