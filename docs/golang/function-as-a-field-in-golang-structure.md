# 作为戈朗结构中的场

> 原文:[https://www . geesforgeks . org/function-as-a-field-in-golang-structure/](https://www.geeksforgeeks.org/function-as-a-field-in-golang-structure/)

Golang 中的一个[结构或 struct](https://www.geeksforgeeks.org/structures-in-golang/) 是用户自定义的类型，它允许我们将一组不同类型的元素创建成一个单元。任何具有一组属性或字段的现实实体都可以表示为一个结构。我们知道，在 Go 语言中[函数](https://www.geeksforgeeks.org/functions-in-go-language/)也是用户定义的类型，因此，您可以在 Go 结构中创建一个函数字段。您也可以使用[匿名函数](https://www.geeksforgeeks.org/anonymous-function-in-go-language/)在 Go 结构中创建一个函数字段，如示例 2 所示。

**语法:**

```go
type function_name func()
type strcut_name struct{
  var_name  function_name
}

```

让我们借助例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate the function
// as a field in Go structure
package main

import "fmt"

// Finalsalary of function type
type Finalsalary func(int, int) int

// Creating structure
type Author struct {
    name      string
    language  string
    Marticles int
    Pay       int

    // Function as a field
    salary Finalsalary
}

// Main method
func main() {

    // Initializing the fields
    // of the structure
    result := Author{
        name:      "Sonia",
        language:  "Java",
        Marticles: 120,
        Pay:       500,
        salary: func(Ma int, pay int) int {
            return Ma * pay
        },
    }

    // Display values
    fmt.Println("Author's Name: ", result.name)
    fmt.Println("Language: ", result.language)
    fmt.Println("Total number of articles published in May: ", result.Marticles)
    fmt.Println("Per article pay: ", result.Pay)
    fmt.Println("Total salary: ", result.salary(result.Marticles, result.Pay))
}
```

**输出:**

```go
Author's Name:  Sonia
Language:  Java
Total number of articles published in May:  120
Per article pay:  500
Total salary:  60000

```

**例 2:**

```go
// Go program to illustrate the function
// as a field in Go structure
// Using anonymous function
package main

import "fmt"

// Creating structure
type Author struct {
    name      string
    language  string
    Tarticles int
    Particles int
    Pending   func(int, int) int
}

// Main method
func main() {

    // Initializing the fields
    // of the structure
    result := Author{
        name:      "Sonia",
        language:  "Java",
        Tarticles: 340,
        Particles: 259,
        Pending: func(Ta int, Pa int) int {
            return Ta - Pa
        },
    }

    // Display values
    fmt.Println("Author's Name: ", result.name)
    fmt.Println("Language: ", result.language)
    fmt.Println("Total number of articles: ", result.Tarticles)

    fmt.Println("Total number of published articles: ",
                                      result.Particles)

    fmt.Println("Pending articles: ", result.Pending(result.Tarticles,
                                                   result.Particles))
}
```

**输出:**

```go
Author's Name:  Sonia
Language:  Java
Total number of articles:  340
Total number of published articles:  259
Pending articles:  81

```