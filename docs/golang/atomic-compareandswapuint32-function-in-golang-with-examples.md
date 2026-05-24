# 原子。用例子比较 Golang 中的函数

> 原文:[https://www . geesforgeks . org/atomic-compareandswapuint32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-compareandswapuint32-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **CompareAndSwapUint32()** 功能用于执行 *uint32* 值的比较和交换操作。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func CompareAndSwapUint32(addr *uint32, old, new uint32) (swapped bool)

```

这里， *addr* 表示地址， *old* 表示 uint32 值为旧值， *new* 是 uint32 新值，它将从旧值交换自身。

**注意:** (*uint32)是指向 uint32 值的指针。uint32 是位大小为 32 的整数类型。此外，int32 包含范围从 0 到 4294967295 的所有无符号 32 位整数的集合。

**返回值:**如果交换完成则返回真，否则返回假。

**例 1:**

```go
// Golang Program to illustrate the usage of
// CompareAndSwapUint32 function

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning variable values to the uint32
    var (
        i uint32 = 34764
    )

    // Calling CompareAndSwapUint32 
    // method with its parameters
    Swap := atomic.CompareAndSwapUint32(&i, 34764, 67576)

    // Displays true if swapped else false
    fmt.Println(Swap)
    fmt.Println("The value of i is: ",i)
}
```

**输出:**

```go
true
The value of i is:  67576

```

**例 2:**

```go
// Golang Program to illustrate the usage of
// CompareAndSwapUint32 function

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning variable values to the uint32
    var (
        i uint32 = 54325
    )

    // Swapping operation
    var oldvalue = atomic.SwapUint32(&i, 7687)

    // Printing old value and swapped value
    fmt.Println("Swapped_value:", i, ", old_value:", oldvalue)

    // Calling CompareAndSwapUint32 method with its parameters
    Swap := atomic.CompareAndSwapUint32(&i, 54325, 677876)

    // Displays true if swapped else false
    fmt.Println(Swap)
    fmt.Println("The value of i is: ",i)
}
```

**输出:**

```go
Swapped_value: 7687 , old_value: 54325
false
The value of i is:  7687

```

这里，从交换操作获得的交换值必须是旧值，这就是为什么返回 false。