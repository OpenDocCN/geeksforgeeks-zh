# Golang |使用接口的多态性

> 原文:[https://www . geesforgeks . org/golang-多态性-使用-接口/](https://www.geeksforgeeks.org/golang-polymorphism-using-interfaces/)

多态这个词意味着有许多形式。或者换句话说，我们可以将多态性定义为一条消息以多种形式显示的能力。或者用专业术语来说，多态性意味着相同的方法名(但是不同的签名)被用于不同的类型。例如，一个女人同时可以有不同的特征。比如母亲、妻子、姐姐、员工等等。所以同一个人在不同的情况下有不同的行为。这叫做多态性。
在 Go 语言中，我们无法借助类来实现多态性，因为 Go 语言不支持类，但是可以通过使用[接口](https://www.geeksforgeeks.org/interfaces-in-golang/)来实现。正如我们已经知道的，接口是在 Go 中隐式实现的。因此，当我们创建一个接口，而其他类型想要实现该接口时，这些类型在接口中定义的方法的帮助下使用该接口，而不需要知道该类型。在接口中，接口类型的变量可以包含实现接口的任何值。该属性有助于接口在 Go 语言中实现多态性。让我们借助一个例子来讨论一下:

**示例:**

```go
// Go program to illustrate the concept
// of polymorphism using interfaces
package main

import "fmt"

// Interface
type employee interface {
    develop() int
    name() string
}

// Structure 1
type team1 struct {
    totalapp_1 int
    name_1     string
}

// Methods of employee interface are
// implemented by the team1 structure
func (t1 team1) develop() int {
    return t1.totalapp_1
}

func (t1 team1) name() string {
    return t1.name_1
}

// Structure 2
type team2 struct {
    totalapp_2 int
    name_2     string
}

// Methods of employee interface are
// implemented by the team2 structure
func (t2 team2) develop() int {
    return t2.totalapp_2
}

func (t2 team2) name() string {
    return t2.name_2
}

func finaldevelop(i []employee) {

    totalproject := 0
    for _, ele := range i {

        fmt.Printf("\nProject environment = %s\n ", ele.name())
        fmt.Printf("Total number of project %d\n ", ele.develop())
        totalproject += ele.develop()
    }
    fmt.Printf("\nTotal projects completed by "+
        "the company = %d", totalproject)
}

// Main function
func main() {

    res1 := team1{totalapp_1: 20,
        name_1: "Android"}

    res2 := team2{totalapp_2: 35,
        name_2: "IOS"}

    final := []employee{res1, res2}
    finaldevelop(final)

}
```

**输出:**

```go
Project environment = Android
 Total number of project 20

Project environment = IOS
 Total number of project 35

Total projects completed by the company = 55

```

**说明:**在上面的例子中，我们有一个作为员工的接口名称。该界面包含两种方法，即 *develop()* 和 *name()* 方法，这里， *develop()* 方法返回项目总数， *name()* 方法返回开发它们的环境名称。

现在我们有两个结构，即*团队 1* 和*团队 2* 。两个结构都包含两个字段，即 *totalapp_1 int* 、 *name_1 string* 、 *totalapp_2 int* 、 *name_2 string* 。现在，这些结构(即*团队 1* 、*团队 2* )正在实现员工界面的方法。

之后，我们创建一个名为 *finaldevelop()* 的函数，返回公司开发的项目总数。它接受员工接口的一部分作为参数，并通过迭代该部分来计算公司开发的项目总数，并在其每个元素上调用 *develop()* 方法。它还通过调用*名称()*方法显示项目的环境。根据员工界面的具体类型，会调用不同的 *develop()* 和 *name()* 方法。因此，我们在 *finaldevelop()* 函数中实现了多态性。

如果在这个实现员工接口的程序中添加另一个团队，这个 *finaldevelop()* 函数将计算公司开发的项目总数，不会因为多态性而有任何变化。