# 原子。Golang 中的 StorePointer()函数示例

> 原文：[https://www.geeksforgeeks.org/atomic-storepointer-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-storepointer-function-in-golang-with-examples/)

在 Go 语言中，`atomic`包提供低级原子内存，有助于实现同步算法。Go 语言中的`StorePointer()`函数用于将`val`自动存储到`addr`中。这个函数是在`atomic`包下定义的。在这里，你需要导入`"sync/atomic"`包来使用这些功能。

## 语法：

```go
func StorePointer(addr *unsafe.Pointer, val unsafe.Pointer)
```

这里，`addr`表示地址。

**注意：**`(*unsafe.Pointer)`是指向`unsafe.Pointer`值。还有`unsafe.Pointer`类型有助于实现任意类型和内置类型之间的转换。而且，`unsafe`是一个有助于 Go 程序类型安全的包。

## 返回值：

将`val`存储到`addr`中，需要时可以返回。

## 例 1：

```go
// Program to illustrate the usage of
// StorePointer function in Golang

// Including main package
package main

// importing fmt, 
// sync/atomic and unsafe
import (
    "fmt"
    "sync/atomic"
    "unsafe"
)

// Defining a struct type L
type L struct{ x, y, z int }

// Declaring pointer 
// to L struct type
var PL *L

// Calling main
func main() {

    // Defining *addr unsafe.Pointer
    var unsafepL = (*unsafe.Pointer)(unsafe.Pointer(&PL))

    // Defining value 
    // of unsafe.Pointer
    var px L

    // Calling StorePointer and 
    // storing unsafe.Pointer
    // value to *addr
    atomic.StorePointer(
        unsafepL, unsafe.Pointer(&px))

    // Printed if value is stored
    fmt.Println("Val Stored!")
}
```

## 输出：

```go
Val Stored!
```

这里，值`unsafe.Pointer`存储在`addr`中，这就是上面的代码返回指定输出的原因。

## 例 2：

```go
// Program to illustrate the usage of
// StorePointer function in Golang

// Including main package
package main

// importing fmt, 
// sync/atomic and unsafe
import (
    "fmt"
    "sync/atomic"
    "unsafe"
)

// Defining a struct type L
type L struct{ x, y, z int }

// Declaring pointer to L struct type
var PL *L

// Calling main
func main() {

    // Defining *addr unsafe.Pointer
    var unsafepL = (*unsafe.Pointer)(unsafe.Pointer(&PL))

    // Defining value 
    // of unsafe.Pointer
    var px = 54634763

    // Calling StorePointer and
    // storing unsafe.Pointer
    // value to *addr
    atomic.StorePointer(
        unsafepL, unsafe.Pointer(&px))

    // Prints the value of the
    // address where val is stored
    fmt.Println(&px)
}
```

## 输出：

```go
0xc0000b6010  // Can be different at different run times
```

在此，所述`unsafe.Pointer` val 被存储，存储的`val`的地址在此返回。此外，在不同的运行时间，地址可以不同。