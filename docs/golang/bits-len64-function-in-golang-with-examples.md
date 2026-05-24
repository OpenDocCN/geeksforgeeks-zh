# 位。Len64()在 Golang 中的作用举例

> 原文:[https://www . geesforgeks . org/bits-len 64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-len64-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供 **Len64()函数**，用来求表示 a 所需的最小位数，对于 a == 0，结果为 0。要访问 Len64()函数，您需要借助 import 关键字在程序中添加一个数学/位包。

**语法:**

```go
func Len64(a uint64) (n int)
```

**参数:**该函数取 uint64 类型的一个参数，即 a。

**返回值:**该函数返回表示一个

**例 1:**

```go
// Golang program to illustrate bits.Len64() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using Len64() function
    a := bits.Len64(1)
    fmt.Printf("The minimum number of bits"+
      " required to represent %d: %d", 1, a)

}
```

**输出:**

```go
The minimum number of bits required to represent 1: 1
```

**例 2 :**

```go
// Golang program to illustrate bits.Len64() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using Len64() function
    a1 := bits.Len64(5)
    fmt.Printf("Len64(%064b) = %d\n", 5, a1)

    a2 := bits.Len64(12)
    fmt.Printf("Len64(%064b) = %d\n", 12, a2)

}
```

**输出:**

```go
Len64(0000000000000000000000000000000000000000000000000000000000000101) = 3
Len64(0000000000000000000000000000000000000000000000000000000000001100) = 4

```