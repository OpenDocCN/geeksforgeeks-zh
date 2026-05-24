# 原子。Golang 中 LoadUint64()函数示例

> 原文:[https://www . geesforgeks . org/atomic-loaduint64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-loaduint64-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供较低级别的原子内存，这有助于实现同步算法。Go 语言中的 **LoadUint64()** 函数用于自动加载 **addr* 。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func LoadUint64(addr *uint64) (val uint64)

```

这里， *addr* 表示地址。

**注意:** (*uint64)是指向 uint64 值的指针。但是，uint64 包含从 0 到 18446744073709551615 的所有无符号 64 位整数的集合。

**返回值:**返回加载到*addr 的值。

**例 1:**

```go
// Program to illustrate the usage of
// LoadUint64 function in Golang

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning values to the uint64
    var (
        i uint64 = 587786787
        j uint64 = 9
        k uint64 = 78678844556666
        l uint64 = 3446
    )

    // Calling LoadUint64 method
    // with its parameters
    load_1 := atomic.LoadUint64(&i)
    load_2 := atomic.LoadUint64(&j)
    load_3 := atomic.LoadUint64(&k)
    load_4 := atomic.LoadUint64(&l)

    // Displays the uint64 value
    // loaded in the *addr
    fmt.Println(load_1)
    fmt.Println(load_2)
    fmt.Println(load_3)
    fmt.Println(load_4)
}
```

**输出:**

```go
587786787
9
78678844556666
3446

```

**例 2:**

```go
// Program to illustrate the usage of
// LoadUint64 function in Golang

// Including main package
package main

// Importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Declaring u
    var u uint64

    // For loop
    for i := 4; i < 200; i += 1 {

        // Function with AddUint64 method
        go func() {
            atomic.AddUint64(&u, 6)
        }()
    }

    // Prints loaded values address
    fmt.Println(atomic.LoadUint64(&u))
}
```

**输出:**

```go
1068    // A random value is returned in each run

```

在上面的例子中，每次调用都会从 *AddUint64()* 方法返回新值，直到循环停止，LoadUint64()方法会加载这些新的 Uint64 值。这些值存储在不同的地址中，这些地址可以是随机的，所以 LoadUint32()方法在每次运行中的输出是不同的。因此，这里在输出中返回一个随机值。