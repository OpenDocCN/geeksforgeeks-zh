# 如何在 Golang 中打印结构变量数据？

> 原文:[https://www . geesforgeks . org/how-print-struct-variables-data-in-golang/](https://www.geeksforgeeks.org/how-to-print-struct-variables-data-in-golang/)

结构(Structure)是 Golang 中用户定义的类型，它包含命名字段/属性的集合，通过组合一个或多个类型来创建自己的数据类型。此外，这个概念通常与面向对象编程中的类进行比较。结构具有相同或不同数据类型的不同字段，并通过组成一组固定的唯一字段来声明。

**语法:**

```go
type StructName struct {
    field1 fieldType1
    field2 fieldType2
}

```

**结构变量:**

```go
variable_name := structure_variable_type {value1, value2...valuen}

```

在 Golang 中有两种打印结构变量的方法。第一种方法是在参数 printing format 参数中使用带有特殊标记的 package fmt 的 Printf 函数。其中一些论点如下:

```go
%v the value in a default format
%+v the plus flag adds field names
%#v a Go-syntax representation of the value

```

**例 1:**

```go
// Go program to print struct variables data
package main

import (
    "fmt"
)

// Creating a structure
type Employee struct {
    Name   string
    Age    int
    Salary int
}

// Main function
func main() {
    // Creating variables
    // of Employee structure
    var e Employee
    e.Name = "Simran"
    e.Age = 23
    e.Salary = 30000

    // Print variable name, value and type
    fmt.Printf("%s\n", e.Name)
    fmt.Printf("%d\n", e.Age)
    fmt.Printf("%d\n", e.Salary)
    fmt.Printf("%#v\n", e)
}
```

**输出:**

```go
Simran
23
30000
main.Employee{Name:"Simran", Age:23, Salary:30000}

```

**例 2:**

```go
// Go program to print struct variables data
package main

import "fmt"

type Mobiles struct {
    company   string
    price     int
    mobile_id int
}

func main() {

    // Declare Mobile1 of type Mobile
    var Mobile1 Mobiles

    // Declare Mobile2 of type Mobile
    var Mobile2 Mobiles

    // Mobile 1 specification
    Mobile1.company = "Vivo"
    Mobile1.price = 20000
    Mobile1.mobile_id = 1695206

    // Mobile 2 specification
    Mobile2.company = "Motorola"
    Mobile2.price = 25000
    Mobile2.mobile_id = 2625215

    // print Mobile1 info
    fmt.Printf("Mobile 1 company : %s\n", Mobile1.company)
    fmt.Printf("Mobile 1 price : %d\n", Mobile1.price)
    fmt.Printf("Mobile 1 mobile_id : %d\n", Mobile1.mobile_id)

    // print Mobile2 info
    fmt.Printf("Mobile 2 company : %s\n", Mobile2.company)
    fmt.Printf("Mobile 2 price : %d\n", Mobile2.price)
    fmt.Printf("Mobile 2 mobile_id : %d\n", Mobile2.mobile_id)
}
```

**输出:**

```go
Mobile 1 company : Vivo
Mobile 1 price : 20000
Mobile 1 mobile_id : 1695206
Mobile 2 company : Motorola
Mobile 2 price : 25000
Mobile 2 mobile_id : 2625215

```

要了解这个，可以参考[这篇](https://www.geeksforgeeks.org/printing-struct-variables-in-golang/)文章。