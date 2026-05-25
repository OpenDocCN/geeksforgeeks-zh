# 原子：用例子比较 Golang 中的函数

> 原文：[https://www.geeksforgeeks.org/atomic-compareandswappointer-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-compareandswappointer-function-in-golang-with-examples/)

在 Go 语言中，`atomic`包提供低级原子内存，有助于实现同步算法。Go 语言中的`CompareAndSwapPointer()`函数用于对一个`unsafe.Pointer`值执行比较和交换操作。这个函数是在`atomic`包下定义的。在这里，您需要导入`sync/atomic`包才能使用这些功能。

## 语法

```go
func CompareAndSwapPointer(addr *unsafe.Pointer, old, new unsafe.Pointer) (swapped bool)
```

这里，`addr`表示地址，`old`表示`unsafe.Pointer`值，是从交换操作返回的旧交换值，而`new`是`unsafe.Pointer`新值，将从旧的交换值中交换。

## 注意

`(*unsafe.Pointer)`是指向一个`unsafe.Pointer`值的指针。`unsafe.Pointer`类型有助于实现任意类型和内置`uintptr`类型之间的转换。而且，`unsafe`是一个有助于 Go 程序类型安全的包。

## 返回值

如果交换完成则返回`true`，否则返回`false`。

## 例 1

```go
// Program to illustrate the usage of
// CompareAndSwapPointer function in Golang

// Including main package
package main

// Importing fmt,
// sync/atomic and unsafe
import (
    "fmt"
    "sync/atomic"
    "unsafe"
)

// Defining a struct type P
type P struct{ x, y, z int }

// Declaring pointer
// to P struct type
var pP *P

// Main function
func main() {

    // Defining addr unsafe.Pointer
    var unsafe1 = (*unsafe.Pointer)(unsafe.Pointer(&pP))

    // Old unsafe pointer
    var sy P

    // Defining new unasfe.pointer
    px := atomic.SwapPointer(
        unsafe1, unsafe.Pointer(&sy))

    // Calling CompareAndSwapPointer
    // method with its parameters
    y := atomic.CompareAndSwapPointer(
        unsafe1, unsafe.Pointer(&sy), px)

    // Returns true if
    // swapped else false
    fmt.Println(y)
}
```

## 输出

```go
true
```

## 例 2

```go
// Program to illustrate the usage of
// CompareAndSwapPointer function in Golang

// Including main package
package main

// importing fmt,
// sync/atomic and unsafe
import (
    "fmt"
    "sync/atomic"
    "unsafe"
)

// Defining a struct type P
type P struct{ x, y, z int }

// Declaring pointer to P struct type
var pP *P

// Main function
func main() {

    // Defining addr unsafe.Pointer
    var unsafe1 = (*unsafe.Pointer)(unsafe.Pointer(&pP))

    // Old unsafe pointer
    var sy P

    // Defining new unasfe.pointer
    px := atomic.SwapPointer(
        unsafe1, unsafe.Pointer(&sy))

    // Calling CompareAndSwapPointer
    // method with its parameters
    y := atomic.CompareAndSwapPointer(
        unsafe1, px, unsafe.Pointer(&sy))

    // Returns true if
    // swapped else false
    fmt.Println(y)
}
```

## 输出

```go
false
```

在上面的例子中，在`CompareAndSwapPointer()`方法中没有执行交换，因为旧值必须是从`SwapPointer()`方法返回的值，但是这里旧值不同，所以从上面的代码中返回`false`。