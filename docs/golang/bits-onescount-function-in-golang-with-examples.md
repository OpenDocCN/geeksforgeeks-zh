# 位。Golang 中的 OnesCount()函数示例

> 原文:[https://www . geesforgeks . org/bits-one count-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-onescount-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 **OnesCount()函数**，用于查找 a 中的一位数，要访问 OnesCount()函数，需要在 import 关键字的帮助下，在程序中添加一个数学/位包。

**语法:**

```go
func OnesCount(a uint) int
```

**参数:**该函数取 uint 类型的一个参数，即 a.
**返回值:**该函数返回用于表示 a 的一位的总数

**例 1:**

```go
// Golang program to illustrate bits.OnesCount() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using OnesCount() function
    a := bits.OnesCount(3)
    fmt.Printf("Total number of one bits "+
     "that are used to represent %d: %d", 3, a)

}
```

**输出:**

```go
Total number of one bits that are used to represent 3: 2
```

**例 2:**

```go
// Golang program to illustrate bits.OnesCount() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using OnesCount() function
    a1 := bits.OnesCount(5)
    fmt.Printf("OnesCount(%b) = %d\n", 5, a1)

    a2 := bits.OnesCount(12)
    fmt.Printf("OnesCount(%b) = %d\n", 12, a2)

}
```

**输出:**

```go
OnesCount(101) = 2
OnesCount(1100) = 2

```