# 原子。Golang 中的 LoadPointer()函数示例

> 原文:[https://www . geesforgeks . org/atomic-load pointer-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-loadpointer-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供较低级别的原子内存，这有助于实现同步算法。Go 语言中的 **LoadPointer()** 函数用于自动加载 **addr* 。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”和“不安全”包才能使用这些功能。

**语法:**

```go
func LoadPointer(addr *unsafe.Pointer) (val unsafe.Pointer)

```

这里， *addr* 表示地址。

**注意:**(*不安全。指针)是指向一个*不安全的指针。指针*值。还有*不安全。指针*类型有助于实现任意类型和内置 *uintptr* 类型之间的转换。而且，unsafe 是一个有助于 Go 程序类型安全的包。

**返回值:**自动加载*addr 并返回*不安全。指针*。

**例 1:**

```go
// Program to illustrate the usage of
// LoadPointer function in Golang

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

    // Calling LoadPointer() method
    px1 := (*L)(atomic.LoadPointer(unsafepL))

    // Returns true if *addr is 
    // loaded else returns false
    fmt.Println(px1 == &px)

    // Prints unsafe.Pointer
    fmt.Println(&px1)
}
```

**输出:**

```go
true
0xc0000b8018 // Can be different at different run times

```

这里， *StorePointer* 方法为 **addr* 添加值，然后 *LoadPointer* 方法自动加载*addr。因此，这里加载完成，返回 true，并且*的值不安全。这里返回的指针*在不同的运行时间可以不同。

**例 2:**

```go
// Program to illustrate the usage of
// LoadPointer function in Golang

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

    // Calling LoadPointer() method
    px1 := (*L)(atomic.LoadPointer(unsafepL))

    // Returns true if *addr is 
    // loaded else returns false
    fmt.Println(px1 == &px)

    // Prints unsafe.Pointer
    fmt.Println(&px1)
}
```

**输出:**

```go
false
0xc00000e028  // A random value is returned in each run

```

这里返回 false，因为这里以前没有存储不安全指针，所以 *LoadPointer()方法*无法加载 **addr* 。而且这里返回的地址值是 *px1* 的地址。