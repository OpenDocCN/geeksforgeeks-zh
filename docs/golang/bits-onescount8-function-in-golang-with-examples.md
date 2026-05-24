# 位。Golang 中的 OnesCount8()函数及示例

> 原文:[https://www . geesforgeks . org/bits-one count 8-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-onescount8-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了**onecount 8()函数**，用于查找 a 中的一位数，要访问 onecount 8()函数，需要在 import 关键字的帮助下，在程序中添加一个数学/位包。

**语法:**

```go
func OnesCount8(a uint8) int
```

**参数:**该函数取 uint8 类型的一个参数，即 a。

**返回值:**该函数返回用于表示一个

**例 1:**

```go
// Golang program to illustrate bits.OnesCount8() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using OnesCount8() function
    a := bits.OnesCount8(5)
    fmt.Printf("Total number of one bits that"+
        " are used to represent %d: %d", 5, a)

}
```

**输出:**

```go
Total number of one bits that are used to represent 5: 2
```

**例 2:**

```go
// Golang program to illustrate bits.OnesCount8() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using OnesCount8() function
    a1 := bits.OnesCount8(4)
    fmt.Printf("OnesCount8(%08b) = %d\n", 4, a1)

    a2 := bits.OnesCount8(13)
    fmt.Printf("OnesCount8(%08b) = %d\n", 13, a2)

}
```

**输出:**

```go
OnesCount8(00000100) = 1
OnesCount8(00001101) = 3

```