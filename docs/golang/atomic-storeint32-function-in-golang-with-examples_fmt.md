# Go语言中的原子操作：StoreInt32()函数示例

> 原文：[https://www.geeksforgeeks.org/atomic-storeint32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-storeint32-function-in-golang-with-examples/)

在Go语言中，`atomic`包提供低级原子内存操作，有助于实现同步算法。Go语言中的`StoreInt32()`函数用于将`val`原子地存储到`addr`中。这个函数是在`atomic`包下定义的。在这里，您需要导入`sync/atomic`包才能使用这些功能。

**语法：**

```go
func StoreInt32(addr *int32, val int32)
```

这里，`addr`表示地址。

**注意：**`*int32`是指向`int32`值的指针。但是，`int32`包含从-2147483648到2147483647的所有带符号32位整数的集合。

**返回值：**将`val`存储到`addr`中，无返回值。

## 例1

```go
// Program to illustrate the usage of
// StoreInt32 function in Golang

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
        x int32
        y int32
    )

    // Using StoreInt32 method
    // with its parameters
    atomic.StoreInt32(&x, 65)
    atomic.StoreInt32(&y, 3455)

    // Displays the value stored in addr
    fmt.Println(atomic.LoadInt32(&x))
    fmt.Println(atomic.LoadInt32(&y))
}
```

**输出：**

```go
65
3455
```

这里，首先，`int32`值存储在定义的地址中，然后使用上面的`LoadInt32()`方法返回它们。

## 例2

```go
// Program to illustrate the usage of
// StoreInt32 function in Golang

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
        x int32
    )

    // Using StoreInt32 method
    // with its parameters
    atomic.StoreInt32(&x, 8943)

    // Loading the stored val
    z := atomic.LoadInt32(&x)

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