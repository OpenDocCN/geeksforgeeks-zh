# 如何在 Golang 中实例化结构指针地址运算符？

> 原文:[https://www . geesforgeks . org/how-instance-struct-pointer-address-operator-in-golang/](https://www.geeksforgeeks.org/how-to-instantiate-struct-pointer-address-operator-in-golang/)

由于[指针](https://www.geeksforgeeks.org/pointers-in-golang/)是用于存储另一个变量的内存地址的特殊变量，而结构是由不同类型组成的用户定义的数据类型。一个[结构](https://www.geeksforgeeks.org/structures-in-golang/)主要是所有其他数据类型的持有者。通过使用指向结构的指针，我们可以轻松地操作/访问分配给结构的数据。要使用指向结构的指针，我们使用“&”，即**地址运算符**。在 Go lang 中，通过使用指向结构的指针，我们可以访问结构的字段，而无需显式取消对它们的引用。

**示例:**这里我们将一个结构名定义为“shape”，并将值传递给这个结构的字段。此外，我们使用指针打印结构的值。

## Go

```go
// Golang program to show how to instantiate
// Struct Pointer Address Operator
package main

import "fmt"

type shape struct {
    length  int
    breadth int
    color   string
}

func main() {

    // Passing all the parameters
    var shape1 = &shape{10, 20, "Green"}

    // Printing the value struct is holding
    fmt.Println(shape1)

    // Passing only length and color value
    var shape2 = &shape{}
    shape2.length = 10
    shape2.color = "Red"

    // Printing the value struct is holding
    fmt.Println(shape2)

    // Printing the length stored in the struct
    fmt.Println(shape2.length)

    // Printing the color stored in the struct
    fmt.Println(shape2.color)

    // Passing only address of the struct
    var shape3 = &shape{}

    // Passing the value through a pointer
    // in breadth field of the variable
    // holding the struct address
    (*shape3).breadth = 10

    // Passing the value through a pointer
    // in color field of the variable
    // holding the struct address
    (*shape3).color = "Blue"

    // Printing the values stored
    // in the struct using pointer
    fmt.Println(shape3)
}
```

**输出:**

```go
&{10 20 Green}
&{10 0 Red}
10
Red
&{0 10 Blue}
```