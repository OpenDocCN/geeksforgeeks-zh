# 原子。用例子比较 Golang 中的函数

> 原文:[https://www . geesforgeks . org/atomic-compareandswapint 64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-compareandswapint64-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **CompareAndSwapInt64()** 函数用于执行一个 *int64* 值的比较和交换操作。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func CompareAndSwapInt64(addr *int64, old, new int64) (swapped bool)

```

这里， *addr* 表示地址， *old* 表示从交换操作返回的旧交换值 int64 值， *new* 表示将从旧交换值交换自身的 int64 新值。

**注意:** (*int64)是指向 int64 值的指针。int64 是位大小为 64 的整数类型。而且，int64 包含从-9223372036854775808 到 922337203685475807 的所有有符号 64 位整数的集合。

**返回值:**如果交换完成则返回真，否则返回假。

下面的例子说明了上述方法的使用:

**例 1:**

```go
// Golang Program to illustrate the usage of
// CompareAndSwapInt64 function

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning variable values to the int64
    var (
        i int64 = 686788787
    )

    // Swapping
    var old_value = atomic.SwapInt64(&i, 56677)

    // Printing old value and swapped value
    fmt.Println("Swapped:", i, ", old value:", old_value)

    // Calling CompareAndSwapInt64 
    // method with its parameters
    Swap := atomic.CompareAndSwapInt64(&i, 56677, 908998)

    // Displays true if swapped else false
    fmt.Println(Swap)
    fmt.Println("The Value of i is: ",i)
}
```

**输出:**

```go
Swapped: 56677 , old value: 686788787
true
The Value of i is:  908998

```

**例 2:**

```go
// Golang Program to illustrate the usage of
// CompareAndSwapInt64 function

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning variable values to the int64
    var (
        i int64 = 686788787
    )

    // Swapping
    var old_value = atomic.SwapInt64(&i, 56677)

    // Printing old value and swapped value
    fmt.Println("Swapped:", i, ", old value:", old_value)

    // Calling CompareAndSwapInt64 
    // method with its parameters
    Swap := atomic.CompareAndSwapInt64(&i, 686788787, 908998)

    // Displays true if swapped else false
    fmt.Println(Swap)
    fmt.Println(i)
}
```

**输出:**

```go
Swapped: 56677, old value: 686788787
false
56677

```

这里， *CompareAndSwapInt64* 方法中的旧值必须是从 *SwapInt64* 方法返回的交换值。这里不执行交换，所以返回 false。