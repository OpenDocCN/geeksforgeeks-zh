# 原子。用例子比较 Golang 中的函数

> 原文:[https://www . geesforgeks . org/atomic-compareandswapuint64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-compareandswapuint64-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **CompareAndSwapUint64()** 功能用于执行 *uint64* 值的比较和交换操作。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func CompareAndSwapUint64(addr *uint64, old, new uint64) (swapped bool)

```

这里， *addr* 表示地址， *old* 表示 uint64 值为旧值， *new* 是 uint64 新值，它将从旧值交换自身。

**注意:** (*uint64)是指向 uint64 值的指针。uint64 是位大小为 64 的整数类型。此外，int64 包含范围从 0 到 18446744073709551615 的所有无符号 64 位整数的集合。

**返回值:**如果交换完成则返回真，否则返回假。

**例 1:**

```go
// Golang Program to illustrate the usage of
// CompareAndSwapUint64 function

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning variable values to the uint64
    var (
        i uint64 = 34764576575
    )

    // Calling CompareAndSwapUint64 method with its parameters
    Swap := atomic.CompareAndSwapUint64(&i, 34764576575, 575765878)

    // Displays true if swapped else false
    fmt.Println(Swap)
    fmt.Println("The new value of i is: ",i)
}
```

**输出:**

```go
true
The new value of i is:  575765878

```

**例 2:**

```go
// Golang Program to illustrate the usage of
// CompareAndSwapUint64 function

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning variable 
    // values to the uint64
    var (
        i uint64 = 143255757
    )

    // Swapping operation. Here value of i become
    // 4676778904
    var oldvalue = atomic.SwapUint64(&i, 4676778904)

    // Printing old value and swapped value
    fmt.Println("Swapped_value:", i, ", old_value:", oldvalue)

    // Calling CompareAndSwapUint64 
    // method with its parameters
    Swap := atomic.CompareAndSwapUint64(&i, 143255757, 9867757)

    // Displays true if swapped else false
    fmt.Println(Swap)
    fmt.Println("The value of i is: ",i)
}
```

**输出:**

```go
Swapped_value: 4676778904 , old_value: 143255757
false
The value of i is:  4676778904

```

这里，从交换操作获得的交换值必须是旧值。即 4676778904，这就是为什么返回 false。