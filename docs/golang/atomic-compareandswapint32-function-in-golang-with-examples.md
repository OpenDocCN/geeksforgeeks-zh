# 原子。用例子比较 Golang 中的函数

> 原文:[https://www . geesforgeks . org/atomic-compareandswapint 32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-compareandswapint32-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供较低级别的原子内存，这有助于实现同步算法。Go 语言中的 **CompareAndSwapInt32()** 函数用于执行 *int32* 值的比较和交换操作。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func CompareAndSwapInt32(addr *int32, old, new int32) (swapped bool)

```

这里， *addr* 表示地址， *old* 表示从交换操作返回的旧交换值 int32 值， *new* 表示将从旧交换值交换自身的 int32 新值。

**注意:** (*int32)是指向 int32 值的指针。int32 是位大小为 32 的整数类型。此外，int32 包含从-2147483648 到 2147483647 的所有带符号 32 位整数的集合。

**返回值:**如果交换完成则返回真，否则返回假。

**例 1:**

```go
// Golang Program to illustrate the usage of
// CompareAndSwapInt32 function

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning variable values to the int32
    var (
        i int32 = 111
    )

    // Swapping
    var old_value = atomic.SwapInt32(&i, 498)

    // Printing old value and swapped value
    fmt.Println("Swapped:", i, ", old value:", old_value)

    // Calling CompareAndSwapInt32 method with its parameters
    Swap := atomic.CompareAndSwapInt32(&i, 498, 675)

    // Displays true if swapped else false
    fmt.Println(Swap)
    fmt.Println("The Value of i is: ",i)
}
```

**输出:**

```go
Swapped: 498 , old value: 111
true
The Value of i is:  675

```

**例 2:**

```go
// Golang Program to illustrate the usage of
// CompareAndSwapInt32 function

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning variable values to the int32
    var (
        i int32 = 111
    )

    // Swapping
    var old_value = atomic.SwapInt32(&i, 498)

    // Printing old value and swapped value
    fmt.Println("Swapped:", i, ", old value:", old_value)

    // Calling CompareAndSwapInt32
    // method with its parameters
    Swap := atomic.CompareAndSwapInt32(&i, 111, 675)

    // Displays true if
    // swapped else false
    fmt.Println(Swap)
    fmt.Println("The Value of i is: ",i)
}
```

**输出:**

```go
Swapped: 498 , old value: 111
false
The Value of i is:  498

```

这里， *CompareAndSwapInt32* 方法中的旧值必须是从 *SwapInt32* 方法返回的交换值。这里不执行交换，所以返回 false。