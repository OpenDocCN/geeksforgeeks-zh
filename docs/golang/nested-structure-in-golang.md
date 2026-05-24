# 戈朗嵌套结构

> 原文:[https://www.geeksforgeeks.org/nested-structure-in-golang/](https://www.geeksforgeeks.org/nested-structure-in-golang/)

Golang 中的一个[结构或 struct](https://www.geeksforgeeks.org/structures-in-golang/) 是用户自定义的类型，它允许我们将一组不同类型的元素创建成一个单元。任何具有一组属性或字段的现实实体都可以表示为一个结构。Go 语言允许嵌套结构。作为另一个结构的字段的结构称为嵌套结构。或者换句话说，另一个结构中的结构称为嵌套结构。

**语法:**

```go
type struct_name_1 struct{
  // Fields
} 
type struct_name_2 struct{
  variable_name  struct_name_1

}

```

让我们借助例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate
// the nested structure
package main

import "fmt"

// Creating structure
type Author struct {
    name   string
    branch string
    year   int
}

// Creating nested structure
type HR struct {

    // structure as a field
    details Author
}

func main() {

    // Initializing the fields
    // of the structure
    result := HR{

        details: Author{"Sona", "ECE", 2013},
    }

    // Display the values
    fmt.Println("\nDetails of Author")
    fmt.Println(result)
}
```

**输出:**

```go
Details of Author
{{Sona ECE 2013}}

```

**例 2:**

```go
// Golang program to illustrate
// the nested structure
package main

import "fmt"

// Creating structure
type Student struct {
    name   string
    branch string
    year   int
}

// Creating nested structure
type Teacher struct {
    name    string
    subject string
    exp     int
    details Student
}

func main() {

    // Initializing the fields
    // of the structure
    result := Teacher{
        name:    "Suman",
        subject: "Java",
        exp:     5,
        details: Student{"Bongo", "CSE", 2},
    }

    // Display the values
    fmt.Println("Details of the Teacher")
    fmt.Println("Teacher's name: ", result.name)
    fmt.Println("Subject: ", result.subject)
    fmt.Println("Experience: ", result.exp)

    fmt.Println("\nDetails of Student")
    fmt.Println("Student's name: ", result.details.name)
    fmt.Println("Student's branch name: ", result.details.branch)
    fmt.Println("Year: ", result.details.year)
}
```

**输出:**

```go
Details of the Teacher
Teacher's name:  Suman
Subject:  Java
Experience:  5

Details of Student
Student's name:  Bongo
Student's branch name:  CSE
Year:  2

```