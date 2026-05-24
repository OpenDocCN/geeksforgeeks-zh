# 原子。在 Golang 中添加 32()函数并举例

> 原文:[https://www . geesforgeks . org/atomic-addint 32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-addint32-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Golang 中的 **AddInt32()** 功能用于自动将 *delta* 添加到 **addr* 中。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func AddInt32(addr *int32, delta int32) (new int32)
```

这里， *addr* 表示地址，δ表示大于零的少量位。

**注意:** (*int32)是指向 int32 值的指针。此外，int32 包含从-2147483648 到 2147483647 的所有带符号 32 位整数的集合。
**返回值:**自动添加 addr 和 delta 并返回一个新值。

**例 1:**

## 去

```go
// Golang Program to illustrate the usage of
// AddInt32 function

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
        i int32 = 97
        j int32 = 48
        k int32 = 34754567
        l int32 = -355363
    )

    // Assigning constant
    // values to int32
    const (
        x int32 = 4
        y int32 = 2
    )

    // Calling AddInt32 method
    // with its parameters
    res_1 := atomic.AddInt32(&i, y)
    res_2 := atomic.AddInt32(&j, y-1)
    res_3 := atomic.AddInt32(&k, x-1)
    res_4 := atomic.AddInt32(&l, x)

    // Displays the output after adding
    // addr and delta atomically
    fmt.Println(res_1)
    fmt.Println(res_2)
    fmt.Println(res_3)
    fmt.Println(res_4)
}
```

**输出:**

```go
99
49
34754570
-355359
```

**例 2:**

## 去

```go
// Golang Program to illustrate the usage of
// AddInt32 function

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Defining addr of type int32
type addr int32

// function that adds addr and delta
func (x *addr) add() int32 {

    // Calling AddInt32() function
    // with its parameter
    return atomic.AddInt32((*int32)(x), 2)
}

// Main function
func main() {

    // Defining x
    var x addr

    // For loop to increment
    // the value of x
    for i := 1; i < 7; i++ {

        // Displays the new value
        // after adding delta and addr
        fmt.Println(x.add())
    }
}
```

**输出:**

```go
2
4
6
8
10
12
```

在上面的例子中，我们定义了一个函数 *add* ，返回调用 *AddInt32* 方法返回的输出。在主函数中，我们定义了一个“for”循环，它将在每次调用中增加“x”的值。这里，AddInt32()方法的第二个参数是常量，只有第一个参数的值是变量。但是，上一次调用的输出将是下一次调用中 AddInt32()方法的第一个参数的值，直到循环停止。

**让我们看看上面的例子是如何工作的:**

```go
1st parameter = 0, 2nd parameter = 2   // returns ( 0 + 2 = 2)

// Now, the above output is 1st parameter in next call to AddInt32() method
1st parameter = 2, 2nd parameter = 2   // returns ( 2 + 2 = 4)
1st parameter = 4, 2nd parameter = 2   // returns ( 4 + 2 = 6) and so on.
```