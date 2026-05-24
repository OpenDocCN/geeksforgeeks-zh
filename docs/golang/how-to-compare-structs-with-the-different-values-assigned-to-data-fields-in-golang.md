# 如何比较 Golang 中分配给数据字段的不同值的结构？

> 原文:[https://www . geeksforgeeks . org/如何将不同值的结构分配给 golang 中的数据字段/](https://www.geeksforgeeks.org/how-to-compare-structs-with-the-different-values-assigned-to-data-fields-in-golang/)

一个[结构](https://www.geeksforgeeks.org/structures-in-golang/)(结构)是一个用户定义的类型，在 Golang 中包含一个命名字段/属性的集合，它通过组合一个或多个类型来创建自己的数据类型。此外，这个概念通常与面向对象编程中的类进行比较。结构具有相同或不同数据类型的不同字段，并通过组成一组固定的唯一字段来声明。

**定义结构类型:**结构的声明以关键字类型开始，然后定义一个新结构的名称，后跟关键字 struct。之后，花括号开始定义一系列具有名称和类型的数据字段。

**语法:**

```go
type StructName struct {
    field1 fieldType1
    field2 fieldType2
}

```

**示例:**

```go
// Creating a structure
type Employee struct {
    firstName string
        lastName string
            salary int
                age int
}
```

下面的例子用来解释——使用比较运算符，可以比较相同类型的结构。

**例 1:**

```go
// Go program to illustrate the
// concept of Struct comparison
// using == operator
package main

import "fmt"

// Creating a structure
type Employee struct {
    FirstName, LastName string
    Salary              int
    Age                 int
}

// Main function
func main() {

    // Creating variables
    // of Employee structure
    A1 := Employee{
        FirstName: "Seema",
        LastName:  "Singh",
        Salary:    20000,
        Age:       23,
    }

    A2 := Employee{
        FirstName: "Seema",
        LastName:  "Singh",
        Salary:    20000,
        Age:       23,
    }

    // Checking if A1 is equal
    // to A2 or not
    // Using == operator
    if A1 == A2 {

        fmt.Println("Variable A1 is equal to variable A2")

    } else {

        fmt.Println("Variable A1 is not equal to variable A2")
    }
}
```

**输出:**

```go
Variable A1 is equal to variable A2
```

**例 2:**

```go
// Go program to illustrate the
// concept of Struct comparison
// with the Different Values Assigned
package main

import "fmt"

// Creating a structure
type triangle struct {
    side1 float64
    side2 float64
    side3 float64
    color string
}

// Main function
func main() {

    // Creating variables
    // of Triangle structure
    var tri1 = triangle{10, 20, 30, "Green"}
    tri2 := triangle{side1: 20, side2: 10,
                  side3: 10, color: "Red"}

    // Checking if tri1 is equal
    // to tri2 or not
    // Using == operator
    if tri1 == tri2 {
        fmt.Println("True")
    } else {
        fmt.Println("False")
    }

    // Checking if tri3 is equal
    // to tri4 or not
    // Using == operator
    tri3 := new(triangle)
    var tri4 = &triangle{}

    if tri3 == tri4 {
        fmt.Println("True")
    } else {
        fmt.Println("False")
    }
}
```

**输出:**

```go
False
False
```