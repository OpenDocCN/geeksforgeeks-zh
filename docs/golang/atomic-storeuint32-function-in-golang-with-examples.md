# 原子。Golang 中 StoreUint32()函数示例

> 原文:[https://www . geesforgeks . org/atomic-storeuint32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-storeuint32-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **StoreUint32()** 功能用于将 val 自动存储到 **addr* 中。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func StoreUint32(addr *uint32, val uint32)

```

这里， *addr* 表示地址。

**注意:** (*uint32)是指向 uint32 值的指针。但是，int32 包含从 0 到 4294967295 的所有无符号 32 位整数的集合。

**返回值:**将 val 存储到*addr 中，需要时可以返回。

**例 1:**

```go
// Program to illustrate the usage of
// StoreUint32 function in Golang

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
        x uint32
        y uint32
    )

    // Using StoreUint32 method
    // with its parameters
    atomic.StoreUint32(&x, 465559)
    atomic.StoreUint32(&y, 123)

    // Displays the value stored in addr
    fmt.Println(atomic.LoadUint32(&x))
    fmt.Println(atomic.LoadUint32(&y))
}
```

**输出:**

```go
465559
123

```

这里，首先，uint32 值存储在定义的地址中，然后使用上面的 LoadUint32()方法返回它们。

**例 2:**

```go
// Program to illustrate the usage of
// StoreUint32 function in Golang

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
        x uint32
    )

    // Using StoreUint32 method 
    // with its parameters
    atomic.StoreUint32(&x, 67677)

    // Loading the stored val
    z := atomic.LoadUint32(&x)

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