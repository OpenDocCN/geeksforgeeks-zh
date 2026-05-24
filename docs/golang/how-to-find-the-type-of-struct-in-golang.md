# 如何在 Golang 找到 Struct 的类型？

> 原文:[https://www . geesforgeks . org/如何找到 golang 中的结构类型/](https://www.geeksforgeeks.org/how-to-find-the-type-of-struct-in-golang/)

Golang 中的结构或[结构](https://www.geeksforgeeks.org/structures-in-golang/)是用户定义的数据类型，是各种数据字段的组合。每个数据字段都有自己的数据类型，可以是内置的，也可以是其他用户定义的类型。Struct 表示任何具有一组属性/字段的现实实体。Go 不支持类的概念，结构是在这种语言中创建用户定义类型的唯一方法。我们可以通过多种方式识别 Go 中的结构类型:

**方法 1:** ***使用反射包***

您可以使用[反射包](https://golang.org/pkg/reflect/)来查找给定类型的结构。反射包允许在运行时确定变量的类型。

**语法:**

```go
func typeofstruct(x interface{}){
    fmt.Println(reflect.TypeOf(x))
}

```

或者

```go
func typeofstruct(x interface{}){
    fmt.Println(reflect.ValueOf(x).Kind())
}

```

**示例:**

```go
package main

// importing required modules
import (
    "fmt"
    "reflect"
)

//struct Student definition
type Student struct {
    name   string
    rollno int
    phone  int64
    city   string
}

func main() {

    // making a struct instance
    // note: data fields should be entered in the order
    // they are declared in the struct definition
    var st1 = Student{"Raman", 01, 88888888888, "Mumbai"}
    fmt.Println(reflect.TypeOf(st1))
    fmt.Println(reflect.ValueOf(st1).Kind())

    // Naming fields while
    // initializing a struct
    st2 := Student{name: "Naman", rollno: 02, 
            phone: 1010101010, city: "Delhi"}
    fmt.Println(reflect.TypeOf(st2))
    fmt.Println(reflect.ValueOf(st2).Kind())
}
```

**输出:**

```go
main.Student
struct
main.Student
struct

```

方法*反映。类型*返回*主。学生*一边打字一边把*反映过来。类型*返回一个结构。正是因为方法*的体现。类型为*返回类型为 *reflect 的变量。类型*。*反映。类型*包含定义传递的变量的类型的所有信息，在本例中是学生。类型告诉我们这个类型最初是由什么组成的——指针、int、字符串、结构、接口或其他内置数据类型。在我们的例子中，类型是学生，类型是结构。

**方法二:** ***使用类型断言***

检查结构类型的另一种方法是使用[类型开关](https://www.geeksforgeeks.org/switch-statement-in-go/)并做几个类型断言。类型开关串联使用几个类型断言，并运行第一个匹配的类型。在此开关中，案例包含要与开关表达式中的类型进行比较的类型，如果没有匹配的案例，则计算默认案例。

**语法:**

```go
switch optstatement; typeswitchexpression{
case typelist 1: Statement..
case typelist 2: Statement..
...
default: Statement..
}

```

**示例:**

```go
// Golang program to find a struct type
// using type assertions
package main

import "fmt"

// struct Employee definition
type Employee struct {
    name        string
    employee_id int
}

func Teststruct(x interface{}) {
    // type switch
    switch x.(type) {
    case Employee:
        fmt.Println("Employee type")
    case int:
        fmt.Println("int type")
    default:
        fmt.Println("Error")
    }
}

func main() {
    // Declaring and initializing a
    // struct using a struct literal
    t := Employee{"Ram", 1234}
    Teststruct(t)
}
```

**输出:**

```go
Employee type

```