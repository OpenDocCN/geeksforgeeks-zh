# 原子。SwapUint64()在 Golang 中的功能示例

> 原文:[https://www . geesforgeks . org/atomic-swapuint64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-swapuint64-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **SwapUint64()** 函数用于将新值自动存储到 **addr* 中，并返回之前的 **addr* 值。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func SwapUint64(addr *uint64, new uint64) (old uint64)

```

这里， *addr* 表示地址。new 是新的 uint64 值，old 是旧的 uint64 值。

**注意:** (*uint64)是指向 uint64 值的指针。uint64 是位大小为 64 的整数类型。但是，uint64 包含从 0 到 18446744073709551615 的所有无符号 64 位整数的集合。

**返回值:**将新的 uint64 值存储到*addr 中，并返回之前的*addr 值。

**例 1:**

```go
// Program to illustrate the usage of
// SwapUint64 function in Golang

// Including main package
package main

// Importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning value to uint64
    var x uint64 = 10864545453

    // Using SwapUint64 method
    // with its parameters
    var old_val = atomic.SwapUint64(&x, 65353443)

    // Prints new and old value
    fmt.Println("Stored new value: ",
         x, ", Old value: ", old_val)
}
```

**输出:**

```go
Stored new value:  65353443, Old value:  10864545453

```

**例 2:**

```go
// Program to illustrate the usage of
// SwapUint64 function in Golang

// Including main package
package main

// Importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning value to uint64
    var m uint64 = 11735344343
    var n uint64 = 976364747

    // Using SwapUint64 method
    //  with its parameters
    var oldVal1 = atomic.SwapUint64(&m, 11735344343)
    var oldVal2 = atomic.SwapUint64(&n, 6586850111)

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

这里，*旧值 1* 等于“m”，因为要存储在*addr 中的新值与旧值相同，所以返回 true，但是*旧值 2* 不等于“n”，因为旧值与新分配的值不相似。因此，返回 false。