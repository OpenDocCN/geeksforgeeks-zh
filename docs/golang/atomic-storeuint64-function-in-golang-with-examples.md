# 原子。Golang 中 StoreUint64()函数示例

> 原文:[https://www . geesforgeks . org/atomic-storeuint64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-storeuint64-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **StoreUint64()** 功能用于将 val 自动存储到 **addr* 中。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func StoreUint64(addr *uint64, val uint64)

```

这里， *addr* 表示地址。

**注意:** (*uint64)是指向 uint64 值的指针。uint64 是位大小为 64 的整数类型。但是，int64 包含从 0 到 18446744073709551615 的所有无符号 64 位整数的集合。

**返回值:**将 val 存入*addr，需要时可以返回。

**例 1:**

```go
// Program to illustrate the usage of
// StoreUint64 function in Golang

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Defining variables for the
    // address to store the val
    var (
        x uint64
        y uint64
    )

    // Using StoreUint64 method
    // with its parameters
    atomic.StoreUint64(&x, 56576656555555)
    atomic.StoreUint64(&y, 0)

    // Displays the value
    // stored in addr
    fmt.Println(atomic.LoadUint64(&x))
    fmt.Println(atomic.LoadUint64(&y))
}
```

**输出:**

```go
56576656555555
0

```

这里，首先，uint64 值存储在定义的地址中，然后使用上面的 LoadUint64()方法返回它们。

**例 2:**

```go
// Program to illustrate the usage of
// StoreUint64 function in Golang

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Defining variables for
    // the address to store the val
    var (
        x uint64
    )

    // Using StoreUint64 method
    // with its parameters
    atomic.StoreUint64(&x, 111776540544)

    // Loading the stored val
    z := atomic.LoadUint64(&x)

    // Prints true if values
    // are same else false
    fmt.Println(z == x)

    // Prints true if addresses 
    // are same else false
    fmt.Println(&z == &x)
}
```

**输出:**

```go
true
false

```

这里，存储和加载的值是相同的，所以返回 true，但是它们的地址不相同，所以在这种情况下返回 false。