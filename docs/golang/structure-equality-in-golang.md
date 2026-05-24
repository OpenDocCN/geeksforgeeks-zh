# Golang 中的结构等价性

> Original: [https://www.geeksforgeeks.org/structure-equality-in-golang/](https://www.geeksforgeeks.org/structure-equality-in-golang/)

Golang 中的结构或结构是用户定义的类型，它允许我们将一组不同类型的元素创建到单个单元中。 任何具有某些属性或字段集的真实实体都可以表示为结构。 这个概念通常与面向对象编程中的类进行比较。 它可以被称为轻量级类，不支持继承，但支持组合。
在 GO 语言中，如果两个结构类型相同且包含相同的字段值，则可以借助**==Operator**或**DeeplyEquity()方法**进行比较。 如果两个结构彼此相等(就其字段值而言)，则运算符和方法都返回 True，否则返回 False。 而且，如果比较的变量属于不同的结构，则编译器将给出错误。 让我们借助下面的例子来讨论这个概念：

**注意：**DeeplyEquity()方法在“Reflect”包下定义。

**示例 1：**

```go
// Go program to illustrate the
// concept of struct equality
// using == operator

package main

import "fmt"

// Creating a structure
type Author struct {
    name      string
    branch    string
    language  string
    Particles int
}

// Main function
func main() {

    // Creating variables
    // of Author structure
    a1 := Author{
        name:      "Moana",
        branch:    "CSE",
        language:  "Python",
        Particles: 38,
    }

    a2 := Author{
        name:      "Moana",
        branch:    "CSE",
        language:  "Python",
        Particles: 38,
    }

    a3 := Author{
        name:      "Dona",
        branch:    "CSE",
        language:  "Python",
        Particles: 38,
    }

    // Checking if a1 is equal
    // to a2 or not
    // Using == operator
    if a1 == a2 {

        fmt.Println("Variable a1 is equal to variable a2")

    } else {

        fmt.Println("Variable a1 is not equal to variable a2")
    }

    // Checking if a1 is equal
    // to a2 or not
    // Using == operator
    if a2 == a3 {

        fmt.Println("Variable a2 is equal to variable a3")

    } else {

        fmt.Println("Variable a2 is not equal to variable a3")
    }
}
```

发帖主题：Re：Колибри0.7.0

```go
Variable a1 is equal to variable a2
Variable a2 is not equal to variable a3

```

**示例 2：**

```go
// Go program to illustrate the
// concept of struct equality
// using DeepEqual() method
package main

import (
    "fmt"
    "reflect"
)

// Creating a structure
type Author struct {
    name      string
    branch    string
    language  string
    Particles int
}

// Main function
func main() {

    // Creating variables 
    // of Author structure
    a1 := Author{
        name:      "Soana",
        branch:    "CSE",
        language:  "Perl",
        Particles: 48,
    }

    a2 := Author{
        name:      "Soana",
        branch:    "CSE",
        language:  "Perl",
        Particles: 48,
    }

    a3 := Author{
        name:      "Dia",
        branch:    "CSE",
        language:  "Perl",
        Particles: 48,
    }

    // Compairing a1 with a2
    // Using DeepEqual() method
    fmt.Println("Is a1 equal to a2: ", reflect.DeepEqual(a1, a2))

    // Compairing a2 with a3
    // Using DeepEqual() method
    fmt.Println("Is a2 equal to a3: ", reflect.DeepEqual(a2, a3))
}
```

发帖主题：Re：Колибри0.7.0

```go
Is a1 equal to a2:  true
Is a2 equal to a3:  false

```