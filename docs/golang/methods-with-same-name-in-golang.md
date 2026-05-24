# 格朗同名方法

> 原文:[https://www . geesforgeks . org/methods-with-同名 in-golang/](https://www.geeksforgeeks.org/methods-with-same-name-in-golang/)

在 Go 语言中，允许在同一个包中创建两个或多个同名的方法，但是这些方法的接收者必须是不同的类型。该功能在 Go 函数中不可用，意味着不允许在同一个包中创建同名方法，如果尝试这样做，那么编译器会抛出一个错误。

**语法:**

> func(reciver_name_1 Type)方法 _ 名称(参数 _ 列表)(return_type){
> //代码
> }
> 
> func(reciver_name_2 Type)方法 _ 名称(参数 _ 列表)(return_type){
> //代码
> }

让我们借助例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate how to
// create methods of the same name
package main

import "fmt"

// Creating structures
type student struct {
    name   string
    branch string
}

type teacher struct {
    language string
    marks    int
}

// Same name methods, but with
// different type of receivers
func (s student) show() {

    fmt.Println("Name of the Student:", s.name)
    fmt.Println("Branch: ", s.branch)
}

func (t teacher) show() {

    fmt.Println("Language:", t.language)
    fmt.Println("Student Marks: ", t.marks)
}

// Main function
func main() {

    // Initializing values
    // of the structures
    val1 := student{"Rohit", "EEE"}

    val2 := teacher{"Java", 50}

    // Calling the methods
    val1.show()
    val2.show()
}
```

**输出:**

```go
Name of the Student: Rohit
Branch:  EEE
Language: Java
Student Marks:  50

```

**说明:**在上面的例子中，我们有两个同名的方法，即 *show()* 但是有不同类型的接收器。这里第一个 *show()* 方法包含学生类型的 s 接收器，第二个 *show()* 方法包含教师类型的 t 接收器。而在 *main()* 函数中，我们借助两个方法各自的结构变量来调用这两个方法。如果您试图用相同类型的接收器创建这个 *show()* 方法，那么编译器会抛出一个错误。

**例 2:**

```go
// Go program to illustrate how to
// create the same name methods
// with non-struct type receivers
package main

import "fmt"

type value_1 string
type value_2 int

// Creating same name function with
// different types of non-struct receivers
func (a value_1) display() value_1 {

    return a + "forGeeks"
}

func (p value_2) display() value_2 {

    return p + 298
}

// Main function
func main() {

    // Initializing the values
    res1 := value_1("Geeks")
    res2 := value_2(234)

    // Display the results
    fmt.Println("Result 1: ", res1.display())
    fmt.Println("Result 2: ", res2.display())
}
```

**输出:**

```go
Result 1:  GeeksforGeeks
Result 2: 532

```