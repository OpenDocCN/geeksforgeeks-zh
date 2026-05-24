# 原子。SwapInt32()在 Golang 中的功能示例

> 原文:[https://www . geesforgeks . org/atomic-swapint 32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-swapint32-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **SwapInt32()** 函数用于将新值自动存储到 **addr* 中，并返回之前的 **addr* 值。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func SwapInt32(addr *int32, new int32) (old int32)

```

这里， *addr* 表示地址。新的是新的 int32 值，旧的是旧的 int32 值。

**注意:** (*int32)是指向 int32 值的指针。但是，int32 包含从-2147483648 到 2147483647 的所有带符号 32 位整数的集合。

**返回值:**将新的 int32 值存储到*addr 中，并返回之前的*addr 值。

**例 1:**

```go
// Program to illustrate the usage of
// SwapInt32 function in Golang

// Including main package
package main

// Importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning value to int32
    var x int32 = 5435435

    // Using SwapInt32 method 
    // with its parameters
    var old_val = atomic.SwapInt32(&x, 6365654)

    // Prints new and old value
    fmt.Println("Stored new value: ",
         x, ", Old value: ", old_val)
}
```

**输出:**

```go
Stored new value:  6365654, Old value:  5435435

```

**例 2:**

```go
// Program to illustrate the usage of
// SwapInt32 function in Golang

// Including main package
package main

// Importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning value to int32
    var m int32 = 1223344
    var n int32 = 6122082

    // Using SwapInt32 method with its parameters
    var oldVal1 = atomic.SwapInt32(&m, 1223344)
    var oldVal2 = atomic.SwapInt32(&n, 16677)

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