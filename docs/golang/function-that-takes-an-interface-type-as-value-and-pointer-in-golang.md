# Golang 中以接口类型为值和指针的函数

> 原文:[https://www . geesforgeks . org/function-take-a-interface-type-as-value-and-pointer-in-golang/](https://www.geeksforgeeks.org/function-that-takes-an-interface-type-as-value-and-pointer-in-golang/)

[函数](https://www.geeksforgeeks.org/functions-in-go-language/)通常是程序中的代码或语句块，它使用户能够重用相同的代码，最终节省了过多的内存使用，节省了时间，更重要的是，提供了更好的代码可读性。因此，基本上，函数是执行特定任务并将结果返回给调用者的语句的集合。一个函数也可以在不返回任何东西的情况下执行一些特定的任务。

[指针](https://www.geeksforgeeks.org/pointers-in-golang/)在 Go 编程语言或 Golang 中是一个变量，用来存储另一个变量的内存地址。Golang 中的指针也被称为特殊变量。变量用于在系统的特定内存地址存储一些数据。内存地址总是以十六进制格式出现(从 0x 开始，如 0xFFAAF 等)。).

在 Go 语言中，[接口](https://www.geeksforgeeks.org/interfaces-in-golang/)是一个自定义类型，用于指定一组一个或多个方法签名，接口是抽象的，所以不允许创建接口的实例。但是您可以创建一个接口类型的变量，并且可以为这个变量分配一个具体的类型值，该值具有接口所需的方法。或者换句话说，接口是方法的集合，也是自定义类型。

现在，您可以创建一个将接口类型作为值和指针的函数。要理解这个概念，请参见下面的示例:

```go
// Golang Function that takes an interface
// type as value and pointer
package main

import "fmt"

// taking an interface
type CoursePrice interface {
    show(int)
}

// taking a function that accept
// CoursePrice interface as an value
func show(cp CoursePrice, fee int) {
    cp.show(fee)
}

// taking a struct
type Dsa struct {
    Price int
}

func (c Dsa) show(fee int) {
    c.Price = fee
}

// taking a struct
type Placement struct {
    Price int
}

// function accepting a pointer
func (p *Placement) show(fee int) {
    p.Price = fee
}

// main function
func main() {

    first := Dsa{Price: 2499}
    second := Placement{Price: 9999}

    // calling the function
    show(first, 1999)

    // calling the function
    // by passing the address
    show(&second, 7999)

    fmt.Println("DSA Course Fee:", first.Price)
    fmt.Println("Placement100 Course Fee:", second.Price)
}
```

**输出:**

```go
DSA Course Fee: 2499
Placement100 Course Fee: 7999

```