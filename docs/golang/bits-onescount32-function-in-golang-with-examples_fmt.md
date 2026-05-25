# Go语言中的`bits.OnesCount32()`函数及示例

> 原文：[https://www.geeksforgeeks.org/bits-onescount32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-onescount32-function-in-golang-with-examples/)

Go 语言在 `bits` 包的帮助下，为位操作提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 `OnesCount32()` 函数，用来查找一个 `uint32` 类型数值中的二进制表示中“1”的个数。要访问 `OnesCount32()` 函数，需要在 `import` 关键字的帮助下，在程序中添加 `math/bits` 包。

## 语法

```go
func OnesCount32(a uint32) int
```

## 参数

该函数取 `uint32` 类型的一个参数，即 `a`。

## 返回值

该函数返回用于表示一个 `uint32` 类型数值 `a` 的二进制表示中“1”的个数。

## 例 1

```go
// Golang program to illustrate bits.OnesCount32() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    a := bits.OnesCount32(5)
    fmt.Printf("Total number of one bits that"+
        " are used to represent %d: %d", 5, a)

}
```

### 输出

```go
Total number of one bits that are used to represent 5: 2
```

## 例 2

```go
// Golang program to illustrate bits.OnesCount32() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    a1 := bits.OnesCount32(4)
    fmt.Printf("OnesCount32(%032b) := %d\n", 4, a1)

    a2 := bits.OnesCount32(13)
    fmt.Printf("OnesCount32(%032b) := %d\n", 13, a2)

}
```

### 输出

```go
OnesCount32(00000000000000000000000000000100) := 1
OnesCount32(00000000000000000000000000001101) := 3
```