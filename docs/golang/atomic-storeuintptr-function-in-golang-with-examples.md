# 原子。Golang 中 StoreUintptr()函数示例

> 原文:[https://www . geesforgeks . org/atomic-storeuintptr-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-storeuintptr-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **StoreUintptr()** 功能用于将 val 自动存储到 **addr* 中。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func StoreUintptr(addr *uintptr, val uintptr)

```

这里， *addr* 表示地址。

**注意:** (*uintptr)是指向 uintptr 值的指针。uintptr 是一个整数类型，它太大了，不能容纳任何指针的位模式。

**返回值:**将 val 存储到 **addr* 中，需要时可以返回。

**例 1:**

```go
// Program to illustrate the usage of
// StoreUintptr function in Golang

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
        x uintptr
        y uintptr
    )

    // Using StoreUintptr method
    // with its parameters
    atomic.StoreUintptr(&x, 444443)
    atomic.StoreUintptr(&y, 223)

    // Displays the value stored in addr
    fmt.Println(atomic.LoadUintptr(&x))
    fmt.Println(atomic.LoadUintptr(&y))
}
```

**输出:**

```go
444443
223

```

这里，首先，uintptr 值存储在定义的地址中，然后使用上面的 LoadUintptr()方法返回它们。

**例 2:**

```go
// Program to illustrate the usage of
// StoreUintptr function in Golang

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
        x uintptr
    )

    // Using StoreUintptr method
    // with its parameters
    atomic.StoreUintptr(&x, 5255151111)

    // Loading the stored val
    z := atomic.LoadUintptr(&x)

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