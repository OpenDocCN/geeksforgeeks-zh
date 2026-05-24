# 格朗结构中的推广方法

> 原文:[https://www . geesforgeks . org/promoted-methods-in-golang-structure/](https://www.geeksforgeeks.org/promoted-methods-in-golang-structure/)

在 Go [结构](https://www.geeksforgeeks.org/structures-in-golang/)中，提升方法的工作就像 [**提升领域**](https://www.geeksforgeeks.org/promoted-fields-in-golang-structure/) 一样。我们在嵌套结构中使用这个概念，其中一个结构是另一个结构中的字段，只需将该结构的名称添加到另一个结构中，它的行为就像嵌套结构中的匿名字段一样。并且该结构的方法(嵌套结构除外)是嵌套结构的一部分，这种类型的方法被称为提升方法。或者换句话说，提示方法是由子结构实现的，并且可由父结构访问的那些方法。

**要点:**

*   如果子结构和父结构包含名称相同但接收器类型不同的方法，那么这两种方法在父结构中都可用，如示例 2 所示。这里子结构和父结构都包含同名的方法。
*   如果子结构包含两个具有相同名称和相同接收者的方法，那么这些方法不会在父结构中升级，如果您尝试这样做，那么编译器将给出一个错误。

**例 1:**

```go
// Golang program to illustrate the
// concept of the promoted methods
package main

import "fmt"

// Structure
type details struct {

    // Fields of the
    // details structure
    name    string
    age     int
    gender  string
    psalary int
}

// Nested structure
type employee struct {
    post string
    eid  int
    details
}

// Method
func (d details) promotmethod(tsalary int) int {
    return d.psalary * tsalary
}

func main() {

    // Initializing the fields of
    // the employee structure
    values := employee{
        post: "HR",
        eid:  4567,
        details: details{

            name:    "Sumit",
            age:     28,
            gender:  "Male",
            psalary: 890,
        },
    }

    // Promoted fields of the 
    // employee structure
    fmt.Println("Name: ", values.name)
    fmt.Println("Age: ", values.age)
    fmt.Println("Gender: ", values.gender)
    fmt.Println("Per day salary: ", values.psalary)

    // Promoted method of the
    // employee structure
    fmt.Println("Total Salary: ", values.promotmethod(30))

    // Normal fields of
    // the employee structure
    fmt.Println("Post: ", values.post)
    fmt.Println("Employee id: ", values.eid)
}
```

**输出:**

```go
Name:  Sumit
Age:  28
Gender:  Male
Per day salary:  890
Total Salary:  26700
Post:  HR
Employee id:  4567

```

**例 2:**

```go
// Golang program to illustrate the
// concept of the promoted methods
package main

import "fmt"

// Structure
type details struct {

    // Fields of the
    // details structure
    name    string
    age     int
    gender  string
    psalary int
}

// Method 1
func (e employee) promotmethod(tarticle int) int {
    return e.particle * tarticle
}

// Nested structure
type employee struct {
    post     string
    particle int
    eid      int
    details
}

// Method 2
func (d details) promotmethod(tsalary int) int {
    return d.psalary * tsalary
}

// Main method
func main() {

    // Initializing the fields of
    // the employee structure
    values := employee{
        post:     "HR",
        eid:      4567,
        particle: 5,
        details: details{

            name:    "Sumit",
            age:     28,
            gender:  "Male",
            psalary: 890,
        },
    }

    // Promoted fields of
    // the employee structure
    fmt.Println("Name: ", values.name)
    fmt.Println("Age: ", values.age)
    fmt.Println("Gender: ", values.gender)
    fmt.Println("Per day salary: ", values.psalary)

    // Promoted method of 
    // the employee structure
    fmt.Println("Total Salary: ", values.promotmethod(30))

    // Normal fields of
    // the employee structure
    fmt.Println("Post: ", values.post)
    fmt.Println("Employee id: ", values.eid)
    fmt.Println("Total Articles: ", values.promotmethod(30))
}
```

**输出:**

```go
Name:  Sumit
Age:  28
Gender:  Male
Per day salary:  890
Total Salary:  150
Post:  HR
Employee id:  4567
Total Articles:  150

```