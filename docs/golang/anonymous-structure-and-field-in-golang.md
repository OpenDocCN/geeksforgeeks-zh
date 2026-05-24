# 戈朗匿名结构和字段

> 原文:[https://www . geesforgeks . org/anonymous-structure-and-field-in-golang/](https://www.geeksforgeeks.org/anonymous-structure-and-field-in-golang/)

Golang 中的结构或 struct 是用户定义的类型，它允许我们将一组不同类型的元素创建成一个单元。任何具有一组属性或字段的现实实体都可以表示为一个结构。

#### 匿名结构

在 Go 语言中，您可以创建匿名结构。匿名结构是不包含名称的结构。当您想要创建一次性可用结构时，它非常有用。您可以使用以下语法创建匿名结构:

```go
variable_name := struct{
// fields
}{// Field_values}

```

让我们借助一个例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate the
// concept of anonymous structure
package main

import "fmt"

// Main function
func main() {

    // Creating and initializing
    // the anonymous structure
    Element := struct {
        name      string
        branch    string
        language  string
        Particles int
    }{
        name:      "Pikachu",
        branch:    "ECE",
        language:  "C++",
        Particles: 498,
    }

    // Display the anonymous structure
    fmt.Println(Element)
}
```

**输出:**

```go
{Pikachu ECE C++ 498}
```

#### 匿名字段

在 Go 结构中，您可以创建匿名字段。匿名字段是那些不包含任何名称的字段，您只需简单地提到字段的类型，Go 将自动使用该类型作为字段的名称。您可以使用以下语法创建结构的匿名字段:

```go
type struct_name struct{
    int
    bool
    float64
}

```

**要点:**

*   In a structure, you are not allowed to create two or more fields of the same type as shown below:

    ```go
    type student struct{
    int
    int
    }

    ```

    如果你试图这样做，那么编译器会给出一个错误。

    *   You are allowed to combine the anonymous fields with the named fields as shown below:

    ```go
    type student struct{
     name int
     price int
     string
    }

    ```

    让我们借助一个例子来讨论匿名字段的概念:

    **示例:**

    ```go
    // Go program to illustrate the
    // concept of anonymous structure
    package main

    import "fmt"

    // Creating a structure
    // with anonymous fields
    type student struct {
        int
        string
        float64
    }

    // Main function
    func main() {

        // Assigning values to the anonymous
        // fields of the student structure
        value := student{123, "Bud", 8900.23}

        // Display the values of the fields
        fmt.Println("Enrollment number : ", value.int)
        fmt.Println("Student name : ", value.string)
        fmt.Println("Package price : ", value.float64)
    }
    ```

    **输出:**

    ```go
    Enrollment number :  123
    Student name :  Bud
    Package price :  8900.23

    ```