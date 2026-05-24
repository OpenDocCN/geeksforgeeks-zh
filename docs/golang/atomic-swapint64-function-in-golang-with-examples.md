# 原子。SwapInt64()在 Golang 中的功能示例

> 原文:[https://www . geesforgeks . org/atomic-swapint 64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-swapint64-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **SwapInt64()** 函数用于将新值自动存储到 **addr* 中，并返回之前的 **addr* 值。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func SwapInt64(addr *int64, new int64) (old int64)

```

这里， *addr* 表示地址。而*新的*是新的 int64 值，*旧的*是旧的 int64 值。

**注意:** (*int64)是指向 int64 值的指针。但是，int64 包含从-9223372036854775808 到 922337203685475807 的所有带符号 64 位整数的集合。

**返回值:**将新的 int64 值存储到*addr 中，并返回之前的*addr 值。

**例 1:**

```go
// Program to illustrate the usage of
// SwapInt64 function in Golang

// Including main package
package main

// Importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning value to int64
    var x int64 = 25786808555

    // Using SwapInt64 method 
    // with its parameters
    var old_val = atomic.SwapInt64(&x, 4567898196323)

    // Prints new and old value
    fmt.Println("Stored new value: ", 
         x, ", Old value: ", old_val)
}
```

**输出:**

```go
Stored new value:  4567898196323, Old value:  25786808555

```

**例 2:**

```go
// Program to illustrate the usage of
// SwapInt64 function in Golang

// Including main package
package main

// Importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning value to int64
    var m int64 = 78453984556
    var n int64 = 364576677888

    // Using SwapInt64 method with its parameters
    var oldVal1 = atomic.SwapInt64(&m, 78453984556)
    var oldVal2 = atomic.SwapInt64(&n, 935128383)

    // Prints output
    fmt.Println((oldVal1) == m)
    fmt.Println((oldVal2) == n)
}
```

**输出:**

```go
true
false

```

这里，*旧值 1* 等于“m”，因为要存储在*addr 中的新值与旧值相同，所以返回 true，但是*旧值 2* 不等于“n”，因为旧值与新分配的值不相似，因此返回 false。