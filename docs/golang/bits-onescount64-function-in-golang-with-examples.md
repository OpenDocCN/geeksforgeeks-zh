# 位。OnesCount64()函数在 Golang 中的示例

> 原文:[https://www . geesforgeks . org/bits-one count 64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-onescount64-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了**onecount 64()函数**，用于查找 a 中的一位数，要访问 onecount 64()函数，需要在导入关键字的帮助下，在程序中添加一个**数学/位**包。

**语法:**

```go
func OnesCount64(a uint64) int
```

**参数:**该函数取 uint64 类型的一个参数，即 a。

**返回值:**该函数返回用于表示一个

**例 1 :**

```go
// Golang program to illustrate bits.OnesCount64() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using OnesCount64() function
    a := bits.OnesCount64(5)
    fmt.Printf("Total number of one bits "+
        "that are used to represent %d: %d", 5, a)

}
```

**输出:**

```go
Total number of one bits that are used to represent 5: 2
```

**例 2 :**

```go
// Golang program to illustrate bits.OnesCount64() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {
    // Using OnesCount64() function
    a1 := bits.OnesCount64(23)
    fmt.Printf("OnesCount64(%064b) := %d\n", 23, a1)

    a2 := bits.OnesCount64(13)
    fmt.Printf("OnesCount64(%064b) := %d\n", 13, a2)

}
```

**输出:**

```go
OnesCount64(0000000000000000000000000000000000000000000000000000000000010111) := 4
OnesCount64(0000000000000000000000000000000000000000000000000000000000001101) := 3

```