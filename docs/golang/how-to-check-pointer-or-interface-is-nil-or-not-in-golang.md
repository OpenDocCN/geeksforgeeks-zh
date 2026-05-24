# 如何检查 Golang 中指针或接口是否为零？

> 原文:[https://www . geeksforgeeks . org/如何检查指针或接口是零或不在 golang/](https://www.geeksforgeeks.org/how-to-check-pointer-or-interface-is-nil-or-not-in-golang/)

在 [Golang](https://www.geeksforgeeks.org/golang/) 中，零校验经常出现在 Golang 代码中，尤其是错误校验。在大多数情况下，**无**检查是直截了当的，但在接口情况下，它有点不同，需要特别注意。

这里的任务是检查指针或接口在 Golang 中是否为零，可以用下面的检查:

**例 1:** 在本例中，检查指针是否为零指针。

```go
// Go program to illustrate how to
// check pointer is nil or not

package main

import (
    "fmt"
)

type Temp struct {
}

func main() {
    var pnt *Temp // pointer
    var x = "123"
    var pnt1 *string = &x

    fmt.Printf("pnt is a nil pointer: %v\n", pnt == nil)
    fmt.Printf("pnt1 is a nil pointer: %v\n", pnt1 == nil)
}
```

**输出:**

```go
pnt is a nil pointer: true
pnt1 is a nil pointer: false

```

**例 2:** 在本例中，检查接口是否为 nil 接口。

```go
// Go program to illustrate how to
// check interface is nil or not

package main

import (
    "fmt"
)

// Creating an interface
type tank interface {

    // Methods
    Tarea() float64
    Volume() float64
}

type myvalue struct {
    radius float64
    height float64
}

// Implementing methods of
// the tank interface
func (m myvalue) Tarea() float64 {

    return 2*m.radius*m.height +
        2*3.14*m.radius*m.radius
}

func (m myvalue) Volume() float64 {

    return 3.14 * m.radius * m.radius * m.height
}

func main() {

    var t tank
    fmt.Printf("t is a nil interface: %v\n", t == nil)

    t = myvalue{10, 14}

    fmt.Printf("t is a nil interface: %v\n", t == nil)

}
```

**输出:**

```go
t is a nil interface: true
t is a nil interface: false

```

**例 3:** 在本例中，检查持有 nil 指针的接口是否为 nil 接口。

```go
// Go program to illustrate how to
// check interface holding a nil
// pointer is nil or not

package main

import (
    "fmt"
)

type Temp struct {
}

func main() {

    // taking a pointer
    var val *Temp

    // taking a interface
    var val2 interface{}

    // val2 is a non-nil interface
    // holding a nil pointer (val)
    val2 = val

    fmt.Printf("val2 is a nil interface: %v\n", val2 == nil)

    fmt.Printf("val2 is a interface holding a nil"+
            " pointer: %v\n", val2 == (*Temp)(nil))
}
```

**输出:**

```go
val2 is a nil interface: false
val2 is a interface holding a nil pointer: true

```