# 原子。Golang 中的 SwapUintptr()函数示例

> 原文:[https://www . geesforgeks . org/atomic-swapuintptr-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-swapuintptr-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **SwapUintptr()** 函数用于将新值自动存储到 **addr* 中，并返回之前的 **addr* 值。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func SwapUintptr(addr *uintptr, new uintptr) (old uintptr)

```

这里， *addr* 表示地址。new 是新的 uintptr 值，old 是旧的 uintptr 值。

**注意:** (*uintptr)是指向 uintptr 值的指针。uintptr 是一个整数类型，它太大了，不能包含任何指针的位模式。

**返回值:**将新的 uintptr 值存储到*addr 中，并返回之前的*addr 值。

**例 1:**

```go
// Program to illustrate the usage of
// SwapUintptr function in Golang

// Including main package
package main

// Importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning value to uintptr
    var x uintptr = 96464646466757

    // Using SwapUintptr method 
    // with its parameters
    var old_val = atomic.SwapUintptr(&x,
                            21863567864)

    // Prints new and old value
    fmt.Println("Stored new value: ",
         x, ", Old value: ", old_val)
}
```

**输出:**

```go
Stored new value:  21863567864, Old value:  96464646466757

```

**例 2:**

```go
// Program to illustrate the usage of
// SwapUintptr function in Golang

// Including main package
package main

// Importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning value to uintptr
    var m uintptr = 4235564747474
    var n uintptr = 2567891937466

    // Using SwapUintptr method with its parameters
    var oldVal1 = atomic.SwapUintptr(&m, 4235564747474)
    var oldVal2 = atomic.SwapUintptr(&n, 7454545419024)

    // Prints output
    fmt.Println((oldVal1) == m)
    fmt.Println((oldVal2) == n)
}
```

**输出:**

```go
true
false

```

这里，*旧值 1* 等于“m”，因为要存储在*addr 中的新值与旧值相同，所以返回 true，但是*旧值 2* 不等于“n”，因为旧值与新分配的值不相似。因此，返回 false。