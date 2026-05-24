# 在格朗控制台打印结构变量

> 原文:[https://www . geesforgeks . org/printing-structure-variables-in-console-in-golang/](https://www.geeksforgeeks.org/printing-structure-variables-in-console-in-golang/)

Golang 中的[结构或结构体](https://www.geeksforgeeks.org/structures-in-golang/)是用户定义的类型，允许将可能不同类型的项目组合成一个类型。任何具有一组属性/字段的现实实体都可以表示为一个结构。这个概念通常与面向对象编程中的类进行比较。它可以被称为不支持继承但支持合成的轻量级类。在控制台上打印结构变量有两种方法，如下所示:

**1。**使用带有以下标签的 Printf 函数

> %v 默认格式的值
> %+v 加号标志添加字段名称
> %#v 值的 Go 语法表示

**示例:**

```go
// Golang program to show how to print
// the struct variables in console
package main

// importing package for printing
import (
    "fmt"
)

// taking a struct
type emp struct {
    name   string
    emp_id int
    salary int
}

func main() {

    // an instance of emp (in 'e')
    e := emp{"GFG", 134, 30000}

    // printing with variable name
    fmt.Printf("%+v", e)

    fmt.Println()

    // printing without variable name
    fmt.Printf("%v", e)
}
```

**输出:**

```go
{name:GFG emp_id:134 salary:30000}
{GFG 134 30000}

```

**2。**使用包编码/json 的 Marshal 打印。

**示例:**

```go
// Golang program to show how to print
// the struct variables in console
package main

import ( 
    "encoding/json"
    "fmt"
) 

// taking a struct
type emp struct {
    Name   string
    Emp_id string
    Salary int
}

func main() {

    // an instance of emp (in 'e')
    var e = emp{ 
        Name:     "GFG", 
        Emp_id:   "123", 
        Salary:    78979854 , 
    } 

    // Marshalling the structure
    // For now ignoring error
    // but you should handle
    // the error in above function
    jsonF, _ := json.Marshal(e)

    // typecasting byte array to string
    fmt.Println(string(jsonF))
}
```

**输出:**

```go
{"Name":"GFG","Emp_id":"123","Salary":78979854}

```