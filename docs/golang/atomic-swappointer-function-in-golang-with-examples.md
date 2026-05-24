# 原子。Golang 中的 SwapPointer()函数示例

> 原文:[https://www . geesforgeks . org/atomic-swappointer-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-swappointer-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **SwapPointer()** 函数用于将新值自动存储到 **addr* 中，并返回之前的 **addr* 值。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func SwapPointer(addr *unsafe.Pointer, new unsafe.Pointer) (old unsafe.Pointer)

```

这里， *addr* 表示地址。而且新的是新的*不安全。指针*值老了就是越老*不安全。指针*值。

**注意:**(*不安全。指针)是指向一个*不安全的指针。指针*值。还有*不安全。指针*类型有助于实现任意类型和内置 *uintptr* 类型之间的转换。而且，unsafe 是一个有助于 Go 程序类型安全的包。

**返回值:**存储新的*不安全。指针*值进入*addr 并返回先前的 **addr* 值。

**例 1:**

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

**输出:**

```go
true
0xc0000c2000  // Can be different at different run times

```

这里， *StorePointer* 方法给*addr 添加值，然后 *SwapPointer* 方法自动将新值存储到 **addr* 中并返回旧值。并且，这里交换完成，因此，返回 true 并且*的值不安全。这里返回的指针*在不同的运行时间可以不同。

**例 2:**

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

**输出:**

```go
false
0xc00000e028  // Can be different at different run times

```

在这里，返回 false，因为这里不安全。指针之前没有被存储，所以 SwapPointer()方法无法交换指定的值。此外，这里返回的地址值是 px1 的地址，并且由于不执行交换，px1 的值将是*零*。