# 原子。Golang 中的 Load()函数示例

> 原文:[https://www . geesforgeks . org/atomic-load-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-load-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **Load()** 功能用于检查 *Store* 方法存储的最新值的值集。此外，如果该*值*没有调用存储方法，也可以返回*无*。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func (v *Value) Load() (x interface{})

```

这里 *v* 是任意类型的值， *x* 是加载和存储方式的输出结果类型的界面。

**注意:**(*值)是指向一个*值*类型的指针。同步/原子标准包中提供的*值*类型用于自动加载和存储任何类型的值。

**返回值:**返回存储方法存储的值集。如果没有调用存储方法，也可以返回*零*。

**例 1:**

```go
// Program to illustrate the usage of
// Load function in Golang

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Defining a struct type L
    type L struct{ x, y, z int }

    // Defining a variable to assign
    // values to the struct type L
    var r1 = L{9, 10, 11}

    // Defining Value type to store
    // values of any type
    var V atomic.Value

    // Calling Store function
    V.Store(r1)

    // Calling Load method
    var r2 = V.Load().(L)

    // Prints values as
    // stored by recent
    // store method
    fmt.Println(r2)

    // Displays true if satisfied
    fmt.Println(r1 == r2)
}
```

**输出:**

```go
{9 10 11}
true

```

在上面的例子中，我们使用了**值**类型来存储任何类型的值。这些值存储在 r1，即所述的接口。但是，可以使用 Load 方法返回这些值。

**例 2:**

```go
// Program to illustrate the usage of
// Load function in Golang

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Defining a struct type L
    type L struct{ x, y, z int }

    // Defining a variable to assign
    // values to the struct type L
    var r1 = L{9, 10, 11}

    // Defining Value type to store
    // values of any type
    var V atomic.Value

    // Calling Load method
    var r2 = V.Load().(L)

    // Prints values as 
    // stored by recent
    // store method
    fmt.Println(r2)

    // Displays true if satisfied
    fmt.Println(r1 == r2)
}
```

**输出:**

```go
panic: interface conversion: interface {} is nil, not main.L

goroutine 1 [running]:
main.main()
    /tmp/sandbox731326366/prog.go:28 +0x240

```

这里，没有调用存储方法，所以返回零。