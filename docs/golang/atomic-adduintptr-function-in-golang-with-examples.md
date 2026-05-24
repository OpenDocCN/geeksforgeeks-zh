# 原子。Golang 中的 AddUintptr()函数示例

> 原文:[https://www . geesforgeks . org/atomic-adduintptr-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-adduintptr-function-in-golang-with-examples/)

在 Go 语言中，*原子*包提供低级原子内存，有助于实现同步算法。Go 语言中的 **AddUintptr()** 功能用于将 *delta* 自动添加到 **addr* 中。这个函数是在原子包下定义的。在这里，您需要导入“同步/原子”包才能使用这些功能。

**语法:**

```go
func AddUintptr(addr *uintptr, delta uintptr) (new uintptr)

```

这里， *addr* 表示地址，δ表示大于零的少量位。

**注意:** (*uintptr)是指向一个 *uintptr* 值的指针。而 *uintptr* 是一个足够大的整数类型，可以保存任何指针的位模式。

**返回值:**自动添加 addr 和 delta，返回新值。

**例 1:**

```go
// Golang Program to illustrate the usage of
// AddUintptr function

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
    // values to the uintptr
    var (
        w uintptr = 0
        x uintptr = 255
        y uintptr = 564688
        z uintptr = 656757686877
    )

    // Assigning constant 
    // values to uintptr
    const (
        m uintptr = 78
        n uintptr = 96
    )

    // Calling AddUintptr method
    // with its parameters
    p_1 := atomic.AddUintptr(&x, (m))
    p_2 := atomic.AddUintptr(&y, ^(n - 1))
    p_3 := atomic.AddUintptr(&z, (2))
    p_4 := atomic.AddUintptr(&w, (n - m))

    // Displays the output after adding
    // addr and delta automically
    fmt.Println(p_1)
    fmt.Println(p_2)
    fmt.Println(p_3)
    fmt.Println(p_4)
}
```

**输出:**

```go
333
564592
656757686879
18

```

**例 2:**

```go
// Golang Program to illustrate the usage of
// AddUintptr function

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Defining addr of type uintptr
type addr uintptr

// function that adds addr and delta
func (p *addr) adds() uintptr {

    // Calling AddUintptr() 
    // function with its
    // parameter
    return atomic.AddUintptr((*uintptr)(p), 32686776785)
}

// Main function
func main() {

    // Defining p
    var p addr

    // For loop to increment 
    // the value of p
    for i := 4; i < 1000; i *= 5 {

        // Displays the new value after
        // adding delta and addr
        fmt.Println(p.adds())
    }
}
```

**输出:**

```go
32686776785
65373553570
98060330355
130747107140

```

在上面的例子中，我们定义了一个函数*添加*，返回调用 *AddUintptr* 方法返回的输出。在主函数中，我们定义了一个“for”循环，它将在每次调用中增加“p”的值。这里，AddUintptr()方法的第二个参数是常量，只有第一个参数的值是变量。但是，上一次调用的输出将是下一次调用中 AddUintptr()方法的第一个参数的值，直到循环停止。

**让我们看看上面的例子是如何工作的:**

```go
1st parameter = 0, 2nd parameter = 32686776785  // returns (0 + 32686776785 = 32686776785)

// Now, the above output is 1st parameter 
// in next call to AddUintptr() method
// It returns (32686776785 + 32686776785 = 65373553570)
1st parameter = 32686776785, 2nd parameter = 32686776785 

// returns (65373553570 + 32686776785 = 130747107140) and so on  
1st parameter = 65373553570, 2nd parameter = 32686776785 

```