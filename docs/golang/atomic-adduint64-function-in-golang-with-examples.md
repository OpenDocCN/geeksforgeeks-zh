# 原子。Golang 中的 AddUint64()函数示例

> 原文:[https://www . geesforgeks . org/atomic-adduint64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-adduint64-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供较低级别的原子内存，这有助于实现同步算法。Go 语言中的 **AddUint64()** 功能用于将 *delta* 自动添加到 **addr* 中。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func AddUint64(addr *uint64, delta uint64) (new uint64)

```

这里， *addr* 表示地址，δ表示大于零的少量位。此外，如果你想从 x 中减去一个有符号的正常数值 c，那么你可以通过 **AddUint64( & x，^uint64(c-1))** 来实现。如果你特别想减少 x，那么可以通过 **AddUint64( & x，^uint64(0))** 来完成。

**注意:** (*uint64)是指向 uint64 值的指针。此外，uint64 包含从 0 到 18446744073709551615 的所有无符号 64 位整数的集合。

**返回值:**它自动添加*地址*和增量，并返回一个新值。

**例 1:**

```go
// Golang Program to illustrate the usage
// of AddUint64 function

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
    // values to the uint64
    var (
        i uint64 = 453
        j uint64 = 167
        k uint64 = 18446744073709551615
        l uint64 = 0
        z int    = 15
    )

    // Assigning constant values to uint64
    const (
        x uint64 = 7
        y uint64 = 12
    )

    // Calling AddUint64 method
    // with its parameters
    a_1 := atomic.AddUint64(&i, -uint64(z))
    a_2 := atomic.AddUint64(&j, ^(y - 1))
    a_3 := atomic.AddUint64(&k, x-1)
    a_4 := atomic.AddUint64(&l, ^uint64(z-1))

    // Displays the output after adding
    // addr and delta automically
    fmt.Println(a_1)
    fmt.Println(a_2)
    fmt.Println(a_3)
    fmt.Println(a_4)
}
```

**输出:**

```go
438
155
5
18446744073709551601

```

**例 2:**

```go
// Golang Program to illustrate the usage
// of AddUint64 function

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Defining addr of type uint64
type addr uint64

// function that adds addr and delta
func (u *addr) adds() uint64 {

    // Calling AddUint64() 
    // function with its
    // parameter
    return atomic.AddUint64((*uint64)(u), 325)
}

// Main function
func main() {

    // Defining u
    var u addr

    // For loop to increment
    // the value of u
    for i := 1; i < 11; i *= 3 {

        // Displays the new value after
        // adding delta and addr
        fmt.Println(u.adds())
    }
}
```

**输出:**

```go
325
650
975

```

在上面的例子中，我们定义了一个函数*添加*，返回调用 *AddUint64* 方法返回的输出。在主函数中，我们定义了一个“for”循环，它将在每次调用中增加“u”的值。这里，AddUint64()方法的第二个参数是常量，只有第一个参数的值是变量。但是，上一次调用的输出将是下一次调用中 AddUint64()方法的第一个参数的值，直到循环停止。

**让我们看看上面的例子是如何工作的:**

```go
1st parameter = 0, 2nd parameter = 325    // returns (0 + 325 = 325)

// Now, the above output is 1st parameter in next call to AddUint64() method
1st parameter = 325, 2nd parameter =  325  // returns (325 + 325 = 650)
1st parameter = 650, 2nd parameter = 325   // returns (650 + 325 = 975)

```