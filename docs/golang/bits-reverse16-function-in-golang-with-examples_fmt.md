# 位。Golang 中的 Reverse16()函数示例

> 原文：[https://www.geeksforgeeks.org/bits-reverse16-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-reverse16-function-in-golang-with-examples/)

## 介绍

Go 语言在 `bits` 包的帮助下，为位操作提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 `Reverse16()` 函数，该函数用于查找一个值的逆序。要访问 `Reverse16()` 函数，您需要在 `import` 关键字的帮助下在程序中添加一个 `math/bits` 包。

## 语法

```go
func Reverse16(a uint16) uint16
```

## 参数

该函数取 `uint16` 类型的一个参数，即 `a`。

## 返回值

该函数返回一个值，其位的顺序相反。

## 例 1

```go
// Golang program to illustrate bits.Reverse16() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using Reverse16() function
    a := bits.Reverse16(5)
    fmt.Printf("Reverse order of %d: %b", 5, a)

}
```

**输出：**

```go
Reverse order of 5: 1010000000000000
```

## 例 2

```go
// Golang program to illustrate bits.Reverse16() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using Reverse16() function
    a1 := bits.Reverse16(9)
    fmt.Printf("Reverse16(%016b) := %b\n", 9, a1)

    a2 := bits.Reverse16(13)
    fmt.Printf("Reverse16(%016b) := %b\n", 13, a2)

}
```

**输出：**

```go
Reverse16(0000000000001001) := 1001000000000000
Reverse16(0000000000001101) := 1011000000000000
```