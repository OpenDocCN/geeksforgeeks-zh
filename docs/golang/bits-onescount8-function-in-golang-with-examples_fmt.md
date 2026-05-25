# Bits.OnesCount8() 函数及示例

> 原文：[https://www.geeksforgeeks.org/bits-onescount8-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-onescount8-function-in-golang-with-examples/)

Go 语言在 `math/bits` 包的帮助下，为位操作提供了内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 `OnesCount8()` 函数，用于查找一个 `uint8` 类型数值中的置位（1）数。要访问 `OnesCount8()` 函数，需要在 `import` 关键字的帮助下，在程序中添加 `math/bits` 包。

## 语法

```go
func OnesCount8(a uint8) int
```

## 参数

该函数取 `uint8` 类型的一个参数，即 `a`。

## 返回值

该函数返回用于表示一个数的二进制形式中置位（1）的总数。

## 例 1

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

**输出：**

```go
Total number of one bits that are used to represent 5: 2
```

## 例 2

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

**输出：**

```go
OnesCount8(00000100) = 1
OnesCount8(00001101) = 3
```