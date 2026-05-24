# 原子。在 Golang 中添加 64()函数并举例

> 原文:[https://www . geesforgeks . org/atomic-addint 64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-addint64-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **AddInt64()** 功能用于自动将 *delta* 添加到 **addr* 中。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func AddInt64(addr *int64, delta int64) (new int64)

```

这里， *addr* 表示地址，δ表示大于零的少量位。

**注意:** (*int64)是指向 int64 值的指针。而且，int64 包含从-9223372036854775808 到 922337203685475807 的所有有符号 64 位整数的集合。

**返回值:**它自动添加 addr 和 delta，并返回一个新值。

**例 1:**

```go
// Golang program to illustrate the usage of
// AddInt64 function

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
    // to the int64
    var (
        s int64 = 67656
        t int64 = 90
        u int64 = 922337203685477580
        v int64 = -9223372036854775807
    )

    // Assigning constant
    // values to int64
    const (
        w int64 = 5
        x int64 = 8
    )

    // Calling AddInt64 method 
    // with its parameters
    output_1 := atomic.AddInt64(&s, w)
    output_2 := atomic.AddInt64(&t, x-w)
    output_3 := atomic.AddInt64(&u, x-6)
    output_4 := atomic.AddInt64(&v, -x)

    // Displays the output after adding
    // addr and delta automically
    fmt.Println(output_1)
    fmt.Println(output_2)
    fmt.Println(output_3)
    fmt.Println(output_4)
}
```

**输出:**

```go
67661
93
922337203685477582
9223372036854775801

```

**例 2:**

```go
// Golang Program to illustrate the usage of
// AddInt64 function

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Defining addr of type int64
type addr int64

// function that adds addr and delta
func (s *addr) adds() int64 {

    // Calling AddInt64() function 
    // with its parameter
    return atomic.AddInt64((*int64)(s), 9)
}

// Main function
func main() {

    // Defining s
    var s addr

    // For loop to increment 
    // the value of s
    for i := 1; i < 10000; i *= 5 {

        // Displays the new value 
        // after adding delta and addr
        fmt.Println(s.adds())
    }
}
```

**输出:**

```go
9
18
27
36
45
54

```

在上面的例子中，我们定义了一个函数*添加*，返回调用 *AddInt64* 方法返回的输出。在主函数中，我们定义了一个“for”循环，它将在每次调用中增加“s”的值。这里，AddInt64()方法的第二个参数是常量，只有第一个参数的值是变量。但是，上一次调用的输出将是下一次调用中 AddInt64()方法的第一个参数的值，直到循环停止。

**让我们看看上面的例子是如何工作的:**

```go
1st parameter = 0, 2nd parameter = 9   // returns (0 + 9 = 9)

// Now, the above output is 1st parameter in next call to AddInt64() method
1st parameter = 9, 2nd parameter = 9   // returns (9 + 9 = 18)
1st parameter = 18, 2nd parameter = 9   // returns (18 + 9 = 27) and so on.

```