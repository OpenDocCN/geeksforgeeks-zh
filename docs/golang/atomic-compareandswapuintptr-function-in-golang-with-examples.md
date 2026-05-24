# 原子。用例子比较 Golang 中的函数

> 原文:[https://www . geesforgeks . org/atomic-compareandswapuintptr-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-compareandswapuintptr-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **CompareAndSwapUintptr()** 功能用于执行 *uintptr* 值的比较和交换操作。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func CompareAndSwapUintptr(addr *uintptr, old, new uintptr) (swapped bool)

```

这里， *addr* 表示地址， *old* 表示 uintptr 值为旧值， *new* 是 uintptr 新值，它将与存储在 addr 中的旧值交换。

**注意:** (*uintptr)是指向 uintptr 值的指针。而 *uintptr* 是一个太大的无符号整数类型，包含任何指针的位模式。

**返回值:**如果交换完成则返回真，否则返回假。

**例 1:**

```go
// Program to illustrate the usage of
// CompareAndSwapUintptr function in Golang

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
    // values to the uintptr
    var (
        i uintptr = 34764686
        j uintptr = 41343432525245
        k uintptr = 0
    )

    // Calling CompareAndSwapUintptr 
    // method with its parameters
    Swap1 := atomic.CompareAndSwapUintptr(&i,
                         34764686, 647567565)

    Swap2 := atomic.CompareAndSwapUintptr(&j,
                          41343432525245, 76)

    Swap3 := atomic.CompareAndSwapUintptr(&k,
                                       0, 15)

    // Displays true if 
    // swapped else false
    fmt.Println(Swap1)
    fmt.Println(Swap2)
    fmt.Println(Swap3)

    // Prints addr
    fmt.Println(i)
    fmt.Println(j)
    fmt.Println(k)
}
```

**输出:**

```go
true
true
true
647567565
76
15

```

**例 2:**

```go
// Program to illustrate the usage of
// CompareAndSwapUintptr function in Golang

// Including main package
package main

// Importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning variable 
    // values to the uintptr
    var (
        x uintptr = 56466244
    )

    // Swapping operation
    var oldvalue = atomic.SwapUintptr(&x, 2344444)

    // Printing old value 
    // and swapped value
    fmt.Println("Swapped_value:", x,
            ", old_value:", oldvalue)

    // Calling CompareAndSwapUintptr 
    // method with its parameters
    Swap := atomic.CompareAndSwapUintptr(&x,
                         56466244, 13232324)

    // Displays true if 
    // swapped else false
    fmt.Println(Swap)
    fmt.Println(x)
}
```

**输出:**

```go
Swapped_value: 2344444, old_value: 56466244
false
2344444

```

在这里，从交换操作中获得的交换值必须是 CompareAndSwapUintptr()方法的旧值，但这里采用的旧值是交换操作的旧值，这是不正确的，这就是为什么返回 false。