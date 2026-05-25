# Golang 中 `atomic.StoreInt64()` 函数示例

> 原文：[https://www.geeksforgeeks.org/atomic-storeint64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-storeint64-function-in-golang-with-examples/)

在 Go 语言中，`atomic` 包提供低级原子内存操作，有助于实现同步算法。Go 语言中的 `StoreInt64()` 函数用于将 `val` 原子地存储到 `addr` 中。这个函数是在 `atomic` 包下定义的。在这里，您需要导入 `sync/atomic` 包才能使用这些功能。

## 语法：

```go
func StoreInt64(addr *int64, val int64)
```

这里，`addr` 表示地址。

## 注意：

`*int64` 是指向 `int64` 值的指针。但是，`int64` 包含从 -9223372036854775808 到 9223372036854775807 的所有带符号 64 位整数的集合。

## 返回值：

将 `val` 存储到 `addr` 中，没有返回值。

## 例 1：

```go
// Program to illustrate the usage of
// StoreInt64 function in Golang

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
        x int64
        y int64
    )

    // Using StoreInt64 method
    // with its parameters
    atomic.StoreInt64(&x, 6777676777)
    atomic.StoreInt64(&y, 98877)

    // Displays the value stored in addr
    fmt.Println(atomic.LoadInt64(&x))
    fmt.Println(atomic.LoadInt64(&y))
}
```

### 输出：

```go
6777676777
98877
```

这里，首先，`int64` 值存储在定义的地址中，然后使用上面的 `LoadInt64()` 方法返回它们。

## 例 2：

```go
// Program to illustrate the usage of
// StoreInt64 function in Golang

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
        x int64
    )

    // Using StoreInt64 method
    // with its parameters
    atomic.StoreInt64(&x, 3654567899788)

    // Loading the stored val
    z := atomic.LoadInt64(&x)

    // Prints true if values
    // are same else false
    fmt.Println(z == x)

    // Prints true if addresses
    // are same else false
    fmt.Println(&z == &x)
}
```

### 输出：

```go
true
false
```

这里，存储和加载的值是相同的，所以返回 `true`，但是它们的地址不相同，所以在这种情况下返回 `false`。