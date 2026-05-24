# 原子。Golang 中的 LoadUintptr()函数示例

> 原文:[https://www . geesforgeks . org/atomic-loaduintptr-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-loaduintptr-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **LoadUintptr()** 函数用于自动加载 **addr* 。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func LoadUintptr(addr *uintptr) (val uintptr)

```

这里， *addr* 表示地址。

**注意:** (*uintptr)是指向 uintptr 值的指针。uintptr 是一个整数类型，它太大了，不能包含任何指针的位模式。

**返回值:**返回加载到 **addr* 的值。

**例 1:**

```go
// Program to illustrate the usage of
// LoadUintptr function in Golang

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning values
    // to the uintptr
    var (
        i uintptr = 98
        j uintptr = 255
        k uintptr = 6576567667788
        l uintptr = 5
    )

    // Calling LoadUintptr method
    // with its parameters
    load_1 := atomic.LoadUintptr(&i)
    load_2 := atomic.LoadUintptr(&j)
    load_3 := atomic.LoadUintptr(&k)
    load_4 := atomic.LoadUintptr(&l)

    // Displays uintptr value
    // loaded in the *addr
    fmt.Println(load_1)
    fmt.Println(load_2)
    fmt.Println(load_3)
    fmt.Println(load_4)
}
```

**输出:**

```go
98
255
6576567667788
5

```

**例 2:**

```go
// Program to illustrate the usage of
// LoadUintptr function in Golang

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
    var u uintptr

    // For loop
    for i := 1; i < 1000; i += 1 {

        // Function with
        // AddUintptr method
        go func() {
            atomic.AddUintptr(&u, 9)
        }()
    }

    // Prints loaded values address
    fmt.Println(atomic.LoadUintptr(&u))
}
```

**输出:**

```go
1818   // A random value is returned in each run

```

在上面的例子中，每次调用都从 *AddUintptr()* 方法返回新值，直到循环停止，LoadUintptr()方法加载这些新的 Uintptr 值。这些值存储在不同的地址中，这些地址可以是随机的，所以 LoadUintptr()方法在每次运行中的输出是不同的。因此，这里在输出中返回一个随机值。