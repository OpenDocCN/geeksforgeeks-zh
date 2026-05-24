# 戈朗结构提升场

> 原文:[https://www . geesforgeks . org/promoted-fields-in-golang-structure/](https://www.geeksforgeeks.org/promoted-fields-in-golang-structure/)

在 Go [结构](https://www.geeksforgeeks.org/structures-in-golang/)中，提升字段就像匿名字段一样，字段的类型就是字段的名称。我们在嵌套结构中使用这个概念，其中一个结构是另一个结构中的字段，只需将该结构的名称添加到另一个结构中，它的行为就像嵌套结构中的匿名字段一样。并且该结构的字段(嵌套结构除外)是嵌套结构的一部分，这种类型的字段称为提升字段。如果匿名结构或嵌套结构和父结构包含具有相同名称的字段，则该字段不会升级，只有不同名称的字段会升级到该结构。

**语法:**

```go
type x struct{
// Fields
}

type y struct{
// Fields of y structure
x
}

```

让我们借助一个例子来讨论这个概念:

**例:**

```go
// Go program to illustrate the
// concept of the promoted fields
package main

import "fmt"

// Structure
type details struct {

    // Fields of the
    // details structure
    name   string
    age    int
    gender string
}

// Nested structure
type student struct {
    branch string
    year   int
    details
}

func main() {

    // Initializing the fields of
    // the student structure
    values := student{
        branch: "CSE",
        year:   2010,
        details: details{

            name:   "Sumit",
            age:    28,
            gender: "Male",
        },
    }

    // Promoted fields of the student structure
    fmt.Println("Name: ", values.name)
    fmt.Println("Age: ", values.age)
    fmt.Println("Gender: ", values.gender)

    // Normal fields of
    // the student structure
    fmt.Println("Year: ", values.year)
    fmt.Println("Branch : ", values.branch)
}
```

**输出:**

```go
Name:  Sumit
Age:  28
Gender:  Male
Year:  2010
Branch :  CSE

```

**说明:**在上面的例子中，我们有两个结构，分别命名为细节和学生。其中细节结构是正常结构，学生结构是嵌套结构，它包含细节结构作为字段，就像匿名字段一样。现在，详细信息结构的字段，即姓名、年龄和性别，被提升到学生结构中，称为提升字段。现在，您可以借助学生结构直接访问它们，如*价值观.姓名*、*价值观.年龄*、*价值观.性别*。