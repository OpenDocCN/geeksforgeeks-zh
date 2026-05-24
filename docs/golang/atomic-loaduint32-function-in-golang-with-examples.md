# 原子。Golang 中 LoadUint32()函数示例

> 原文:[https://www . geesforgeks . org/atomic-loaduint32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-loaduint32-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **LoadUint32()** 函数用于自动加载 **addr* 。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func LoadUint32(addr *uint32) (val uint32)

```

这里， *addr* 表示地址。

**注意:** (*uint32)是指向 uint32 值的指针。但是，uint32 包含从 0 到 4294967295 的所有无符号 32 位整数的集合。

**返回值:**返回加载到*addr 的值。

**例 1:**

```go
// Program to illustrate the usage of
// LoadUint32 function in Golang

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning values to the uint32
    var (
        i uint32 = 57
        j uint32 = 0
        k uint32 = 444
        l uint32 = 45646667
    )

    // Calling LoadUint32 method 
    // with its parameters
    load_1 := atomic.LoadUint32(&i)
    load_2 := atomic.LoadUint32(&j)
    load_3 := atomic.LoadUint32(&k)
    load_4 := atomic.LoadUint32(&l)

    // Displays the uint32 value
    // loaded in the *addr
    fmt.Println(load_1)
    fmt.Println(load_2)
    fmt.Println(load_3)
    fmt.Println(load_4)
}
```

**输出:**

```go
57
0
444
45646667

```

**例 2:**

```go
// Program to illustrate the usage of
// LoadUint32 function in Golang

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
    var u uint32

    // For loop
    for i := 3; i < 315; i++ {

        // Function with AddUint32 method
        go func() {
            atomic.AddUint32(&u, 2)
        }()
    }

    // Prints loaded values address
    fmt.Println(atomic.LoadUint32(&u))
}
```

**输出:**

```go
498    // A random value is returned in each run

```

在上面的例子中，每次调用都从 *AddUint32()* 方法返回新值，直到循环停止，LoadUint32()方法加载这些新的 Uint32 值。这些值存储在不同的地址中，这些地址可以是随机的，所以 LoadUint32()方法在每次运行中的输出是不同的。因此，这里在输出中返回一个随机值。