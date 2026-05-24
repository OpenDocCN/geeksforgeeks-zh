# 指向 Golang 中某个结构的指针

> 原文:[https://www . geesforgeks . org/指针指向一个结构在 golang/](https://www.geeksforgeeks.org/pointer-to-a-struct-in-golang/)

[Golang 中的指针](https://www.geeksforgeeks.org/pointers-in-golang/)是一个变量，用来存储另一个变量的内存地址。Golang 中的指针也被称为特殊变量。变量用于在系统的特定内存地址存储一些数据。

您也可以使用指针指向 [**结构**](https://www.geeksforgeeks.org/structures-in-golang/) 。Golang 中的结构是用户定义的类型，它允许将可能不同类型的项组合成一个类型。要使用指向结构的指针，可以使用 **&** 运算符，即地址运算符。Golang 允许程序员使用指针访问结构的字段，而无需任何显式的解引用。

**示例 1:** 这里，我们正在创建一个名为 Employee 的结构，它有两个变量。在主功能中，创建结构的实例，即 *emp* 。之后，您可以将结构的地址传递给指针，该指针表示指向结构概念的指针。没有必要显式使用取消引用，因为它会给出与您在下面的程序中看到的相同的结果(两次 ABC)。

```go
// Golang program to illustrate the
// concept of the Pointer to struct
package main

import "fmt"

// taking a structure
type Employee struct {

    // taking variables
    name  string
    empid int
}

// Main Function
func main() {

    // creating the instance of the
    // Employee struct type
    emp := Employee{"ABC", 19078}

    // Here, it is the pointer to the struct
    pts := &emp

    fmt.Println(pts)

    // accessing the struct fields(liem employee's name)
    // using a pointer but here we are not using
    // dereferencing explicitly
    fmt.Println(pts.name)

    // same as above by explicitly using
    // dereferencing concept
    // means the result will be the same
    fmt.Println((*pts).name)

}
```

**输出:**

```go
&{ABC 19078}
ABC
ABC

```

**示例 2:** 您也可以使用如下所示的指针来修改结构成员或结构文字的值:

```go
// Golang program to illustrate the
// concept of the Pointer to struct
package main

import "fmt"

// taking a structure
type Employee struct {

    // taking variables
    name  string
    empid int
}

// Main Function
func main() {

    // creating the instance of the
    // Employee struct type
    emp := Employee{"ABC", 19078}

    // Here, it is the pointer to the struct
    pts := &emp

    // displaying the values
    fmt.Println(pts)

    // updating the value of name
    pts.name = "XYZ"

    fmt.Println(pts)

}
```

**输出:**

```go
&{ABC 19078}
&{XYZ 19078}

```