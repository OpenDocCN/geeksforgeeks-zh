# GoLang 中的面向对象编程

> 原文:[https://www . geesforgeks . org/面向对象编程语言/](https://www.geeksforgeeks.org/object-oriented-programming-in-golang/)

[面向对象编程](https://www.geeksforgeeks.org/oops-object-oriented-design/)是一种使用“对象”的思想来表示数据和方法的编程范式。Go 不严格支持面向对象，但它是一种轻量级的面向对象语言。Golang 的面向对象编程不同于其他语言，如 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 或 [Java](https://www.geeksforgeeks.org/java/) ，原因如下:

### 1.结构体

Go 不支持通过类的自定义类型，但支持[结构。](https://www.geeksforgeeks.org/structures-in-golang/)Golang 中的结构是用户定义的类型，只保存状态，不保存行为。结构可用于表示包含多个键值对的复杂对象。我们可以向结构中添加函数，这些函数可以向结构中添加行为，如下所示:

**示例:**

```go
// Golang program to illustrate the
// concept of custom types
package main

import (
    "fmt"
)

// declaring a struct
type Book struct{

    // defining struct variables
    name string
    author string
    pages int
}

// function to print book details
func (book Book) print_details(){

    fmt.Printf("Book %s was written by %s.", book.name, book.author)
    fmt.Printf("\nIt contains %d pages.\n", book.pages)
}

// main function
func main() {

    // declaring a struct instance
    book1 := Book{"Monster Blood", "R.L.Stine", 131}

    // printing details of book1
    book1.print_details()

    // modifying book1 details
    book1.name = "Vampire Breath"
    book1.pages = 162

    // printing modified book1
    book1.print_details()

}
```

**输出:**

```go
Book Monster Blood was written by R.L.Stine.
It contains 131 pages.
Book Vampire Breath was written by R.L.Stine.
It contains 162 pages.

```

### 2.包装

这意味着对用户隐藏敏感数据。在 Go 中，封装是通过将字段、方法和函数大写来实现的，这使得它们成为公共的。当结构、字段或函数公开时，它们在包级别导出。公共和私人成员的一些例子有:

```go
package gfg

// this function is public as 
// it begins with a capital letter
func Print_this(){
        // implementation
}

// public struct
type Book struct{

        // public field
        Name string
        // private field, only
        // available in gfg package
        author string
}

```

### 3.遗产

当一个类获得其超类的属性时，我们可以说它是继承。这里，子类/子类是用于获取属性的类的术语。对于这个，我们必须使用一个结构来实现 Golang 中的继承。在这里，用户必须使用结构来组成其他对象。

### 4.接口

接口是具有多种方法的类型。实现接口的所有方法的对象自动实现接口，即隐式满足接口。通过以一致的方式处理不同类型的对象，只要它们坚持一个接口，Golang 就实现了多态性。

**示例:**

```go
// Golang program to illustrate the
// concept of interfaces
package main

import (
    "fmt"
)

// defining an interface
type Sport interface{

    // name of sport method
    sportName() string
}

// declaring a struct
type Human struct{

    // defining struct variables
    name string
    sport string
}

// function to print book details
func (h Human) sportName() string{

    // returning a string value
    return h.name + " plays " + h.sport + "."
}

// main function
func main() {

    // declaring a struct instance
    human1 := Human{"Rahul", "chess"}

    // printing details of human1
    fmt.Println(human1.sportName())

    // declaring another struct instance
    human2 := Human{"Riya", "carrom"}

    // printing details of human2
    fmt.Println(human2.sportName())
}
```

**输出:**

```go
Rahul plays chess.
Riya plays carrom.

```