# 原子。Golang 中 LoadInt64()函数示例

> 原文:[https://www . geesforgeks . org/atomic-loadint 64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-loadint64-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **LoadInt64()** 函数用于自动加载 **addr* 。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func LoadInt64(addr *int64) (val int64)

```

这里， *addr* 表示地址。

**注意:** (*int64)是指向 int64 值的指针。然而，int64 包含从-9223372036854775808 到 922337203685475807 的所有有符号 64 位整数的集合。

**返回值:**返回加载到 addr 的值。

**例 1:**

```go
// Program to illustrate the usage of
// LoadInt64 function in Golang

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning values to the int64
    var (
        i int64 = 68678677
        j int64 = -45369087334
        k int64 = 0
        l int64 = 75
    )

    // Calling LoadInt64 method with its parameters
    load_1 := atomic.LoadInt64(&i)
    load_2 := atomic.LoadInt64(&j)
    load_3 := atomic.LoadInt64(&k)
    load_4 := atomic.LoadInt64(&l)

    // Displays the int64 value loaded in the *addr
    fmt.Println(load_1)
    fmt.Println(load_2)
    fmt.Println(load_3)
    fmt.Println(load_4)
}
```

**输出:**

```go
68678677
-45369087334
0
75

```

**例 2:**

```go
// Program to illustrate the usage of
// LoadInt64 function in Golang

// Including main package
package main

// Importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Declaring x
    var x int64

    // For loop
    for i := 2; i < 500; i += 3 {

        // Function with AddInt64 method
        go func() {
            atomic.AddInt64(&x, 5)
        }()
    }

    // Prints loaded values address
    fmt.Println(atomic.LoadInt64(&x))
}
```

**输出:**

```go
435   // A random value is returned in each run

```

在上例中，每次调用中从 *AddInt64()* 方法返回的新值直到循环停止都存储在不同的地址中，LoadInt64()方法返回这些新值的地址。这个地址可以是随机的，所以 LoadInt64()方法在每次运行中的输出是不同的。因此，这里在输出中返回一个随机值。