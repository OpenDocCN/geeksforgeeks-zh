# Go语言中的`atomic.SwapPointer()`函数详解

> 原文：[https://www.geeksforgeeks.org/atomic-swappointer-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-swappointer-function-in-golang-with-examples/)

在 Go 语言中，`atomic`包提供低级原子内存操作，有助于实现同步算法。Go 语言中的`SwapPointer()`函数用于将新值自动存储到`addr`中，并返回之前的`addr`值。这个函数是在`atomic`包下定义的。在这里，您需要导入`sync/atomic`包才能使用这些功能。

## 语法

```go
func SwapPointer(addr *unsafe.Pointer, new unsafe.Pointer) (old unsafe.Pointer)
```

这里，`addr`表示地址。`new`是新的`unsafe.Pointer`值。`old`就是先前的`unsafe.Pointer`值。

**注意：** `unsafe.Pointer`是指向一个`unsafe.Pointer`值的指针。`unsafe.Pointer`类型有助于实现任意类型和内置`uintptr`类型之间的转换。而且，`unsafe`是一个有助于 Go 程序类型安全的包。

**返回值：** 将新的`unsafe.Pointer`值存入`addr`并返回先前的`addr`值。

## 例 1

```go
// Program to illustrate the usage of
// SwapPointer function in Golang

// Including main package
package main

// Importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
    "unsafe"
)

// Defining a struct type L
type L struct{ x, y, z int }

// Declaring pointer to L struct type
var PL *L

// Main function
func main() {

    // Defining *addr unsafe.Pointer
    var unsafepL = (*unsafe.Pointer)(unsafe.Pointer(&PL))

    // Defining values
    // of unsafe.Pointer
    var px, py L

    // Storing value to the pointer
    atomic.StorePointer(
        unsafepL, unsafe.Pointer(&px))

    // Calling SwapPointer() method
    px1 := atomic.SwapPointer(unsafepL,
        unsafe.Pointer(&py))

    // Returns true if swapped
    fmt.Println((*L)(px1) == &px)

    // Prints output
    fmt.Println(px1)
}
```

### 输出

```go
true
0xc0000c2000  // Can be different at different run times
```

这里，`StorePointer`方法给`addr`添加值，然后`SwapPointer`方法自动将新值存储到`addr`中并返回旧值。并且，这里交换完成，因此返回`true`，并且`px1`的值是`&py`。这里返回的指针在不同的运行时间可以不同。

## 例 2

```go
// Program to illustrate the usage of
// SwapPointer function in Golang

// Including main package
package main

// Importing fmt and sync/atomic
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

// Main function
func main() {

    // Defining *addr unsafe.Pointer
    var unsafepL = (*unsafe.Pointer)(unsafe.Pointer(&PL))

    // Defining values of unsafe.Pointer
    var px, py L

    // Calling SwapPointer() method
    px1 := atomic.SwapPointer(unsafepL,
        unsafe.Pointer(&py))

    // Returns true if swapped
    fmt.Println((*L)(px1) == &px)

    // Prints output
    fmt.Println(&px1)
}
```

### 输出

```go
false
0xc00000e028  // Can be different at different run times
```

在这里，返回`false`，因为这里`unsafe.Pointer`之前没有被存储，所以`SwapPointer()`方法无法交换指定的值。此外，这里返回的地址值是`px1`的地址，并且由于不执行交换，`px1`的值将是`nil`。