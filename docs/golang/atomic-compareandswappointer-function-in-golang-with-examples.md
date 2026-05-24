# 原子。用例子比较 Golang 中的函数

> 原文:[https://www . geesforgeks . org/atomic-compareandswappointer-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-compareandswappointer-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **CompareAndSwapPointer()** 功能用于对一个*不安全执行比较和交换操作。指针*值。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func CompareAndSwapPointer(addr *unsafe.Pointer, old, new unsafe.Pointer) (swapped bool)

```

这里， *addr* 表示地址， *old* 表示不安全。指针值是从*交换*操作返回的旧交换值，而*新的*是不安全的*。指针*新值将从旧的交换值中交换。

**注意:**(*不安全。指针)是指向一个*不安全的指针。指针*值。还有*不安全。指针*类型有助于实现任意类型和内置 *uintptr* 类型之间的转换。而且，unsafe 是一个有助于 Go 程序类型安全的包。

**返回值:**如果交换完成则返回真，否则返回假。

**例 1:**

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

**输出:**

```go
true

```

**例 2:**

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

**输出:**

```go
false

```

在上面的例子中，在 *CompareAndSwapPointer()方法*中没有执行交换，因为旧值必须是从 *SwapPointer()方法*返回的值，但是这里旧值不同，所以从上面的代码中返回 false。