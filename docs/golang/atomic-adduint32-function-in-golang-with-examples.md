# 原子。Golang 中的 AddUint32()函数示例

> 原文:[https://www . geesforgeks . org/atomic-adduint32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-adduint32-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **AddUint32()** 功能用于将 *delta* 自动添加到 **addr* 中。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func AddUint32(addr *uint32, delta uint32) (new uint32)

```

这里， *addr* 表示地址，δ表示大于零的少量位。此外，如果你想从 x 中减去一个有符号的正常数值 c，那么你可以通过 **AddUint32( & x，^uint32(c-1))** 来实现。如果你特别想减少 x，那么可以通过 **AddUint32( & x，^uint32(0))** 来完成。

**注意:** (*uint32)是指向 uint32 值的指针。uint32 是位大小为 32 的无符号整数类型。此外，uint32 包含从 0 到 4294967295 的所有无符号 32 位整数的集合。

**返回值:**自动添加 addr 和 delta，返回新值。

**例 1:**

```go
// Golang Program to illustrate the usage
// of AddUint32 function

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
        i uint32 = 45
        j uint32 = 67
        k uint32 = 4294967295
        l uint32 = 0
        z int    = 5
    )

    // Assigning constant 
    // values to uint32
    const (
        x uint32 = 6
        y uint32 = 3
    )

    // Calling AddUint32 method
    // with its parameters
    a_1 := atomic.AddUint32(&i, -uint32(z))
    a_2 := atomic.AddUint32(&j, ^(y - 1))
    a_3 := atomic.AddUint32(&k, x-1)
    a_4 := atomic.AddUint32(&l, ^uint32(z-1))

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
40
64
4
4294967291

```

**例 2:**

```go
// Golang program to illustrate the usage
// of the AddUint32 function

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Defining addr of type uint32
type addr uint32

// function that adds addr and delta
func (u *addr) add() uint32 {

    // Calling AddUint32() function
    // with its parameter
    return atomic.AddUint32((*uint32)(u), 4)
}

// Main function
func main() {

    // Defining u
    var u addr

    // For loop to increment the value of u
    for i := 0; i < 17; i += 2 {

        // Displays the new value
        // after adding delta and addr
        fmt.Println(u.add())
    }
}
```

**输出:**

```go
4
8
12
16
20
24
28
32
36

```

在上面的例子中，我们定义了一个函数 *add* ，返回调用 *AddUint32* 方法返回的输出。在主函数中，我们定义了一个“for”循环，它将在每次调用中增加“u”的值。这里，AddUint32()方法的第二个参数是常量，只有第一个参数的值是变量。但是，上一次调用的输出将是下一次调用中 AddUint32()方法的第一个参数的值，直到循环停止。

**让我们看看上面的例子是如何工作的:**

```go
1st parameter = 0, 2nd parameter = 4  // returns (0 + 4 = 4)

// Now, the above output is 1st parameter in next call to AddUint32() method
1st parameter = 4, 2nd parameter = 4   // returns (4 + 4 = 8)
1st parameter = 8, 2nd parameter = 4   // returns (8 + 4 = 12) and so on.

```