# 原子包中的`StoreUintptr()`函数示例

> 原文：[https://www.geeksforgeeks.org/atomic-storeuintptr-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-storeuintptr-function-in-golang-with-examples/)

在 Go 语言中，`atomic`包提供低级原子内存操作，有助于实现同步算法。Go 语言中的`StoreUintptr()`函数用于将`val`原子地存储到`addr`中。这个函数是在`atomic`包下定义的。在这里，您需要导入`sync/atomic`包才能使用这些功能。

**语法：**

```go
func StoreUintptr(addr *uintptr, val uintptr)
```

这里，`addr`表示地址。

**注意：**`*uintptr`是指向`uintptr`值的指针。`uintptr`是一个整数类型，它足够大以容纳任何指针的位模式。

**返回值：** 将`val`存储到`addr`中，没有返回值。

**例 1：**

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

**输出：**

```go

```

这里，首先，`uintptr`值原子地存储在定义的地址中，然后使用上面的`LoadUintptr()`函数返回它们。

**例 2：**

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

**输出：**

```go
true
false
```

这里，存储和加载的值是相同的，所以返回`true`，但是它们的地址不相同，所以在这种情况下返回`false`。