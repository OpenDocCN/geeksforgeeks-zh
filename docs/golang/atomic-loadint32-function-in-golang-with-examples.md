# 原子。Golang 中 LoadInt32()函数示例

> 原文:[https://www . geesforgeks . org/atomic-loadint 32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-loadint32-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **LoadInt32()** 函数用于自动加载 **addr* 。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func LoadInt32(addr *int32) (val int32)

```

这里， *addr* 表示地址。

**注意:** (*int32)是指向 int32 值的指针。但是，int32 包含从-2147483648 到 2147483647 的所有带符号 32 位整数的集合。

**返回值:**返回加载到 addr 的值。

**例 1:**

```go
// Program to illustrate the usage of
// LoadInt32 function in Golang

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

    // Assigning values to the int32
    var (
        i int32 = 57567
        j int32 = -842
        k int32 = 17
        l int32 = 3455
    )

    // Calling LoadInt32 method
    // with its parameters
    load_1 := atomic.LoadInt32(&i)
    load_2 := atomic.LoadInt32(&j)
    load_3 := atomic.LoadInt32(&k)
    load_4 := atomic.LoadInt32(&l)

    // Displays the int32 value 
    // loaded in the *addr
    fmt.Println(load_1)
    fmt.Println(load_2)
    fmt.Println(load_3)
    fmt.Println(load_4)
}
```

**输出:**

```go
57567
-842
17
3455

```

**例 2:**

```go
// Program to illustrate the usage of
// LoadInt32 function in Golang

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
    var x int32

    // For loop
    for i := 1; i < 789; i += 2 {

        // Function with AddInt32 method
        go func() {
            atomic.AddInt32(&x, 4)
        }()
    }

    // Prints loaded values address
    fmt.Println(atomic.LoadInt32(&x))
}
```

**输出:**

```go
1416   // A random value is returned in each run

```

在上面的例子中，每次调用都会从 *AddInt32()* 方法返回新值，直到循环停止，LoadInt32()方法会加载这些新的 Int32 值。这些值存储在不同的地址中，这些地址可以是随机的，所以 LoadInt32()方法在每次运行中的输出是不同的。因此，这里在输出中返回一个随机值。