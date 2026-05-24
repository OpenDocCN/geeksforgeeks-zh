# 如何访问 Golang 中的接口字段？

> 原文:[https://www . geesforgeks . org/如何访问-界面-字段-in-golang/](https://www.geeksforgeeks.org/how-to-access-interface-fields-in-golang/)

Go 语言接口不同于其他语言。在 Go 语言中，接口是一种自定义类型，用于指定一组一个或多个方法签名，并且接口是抽象的，因此不允许您创建接口的实例。但是您可以创建一个接口类型的变量，并且可以为这个变量分配一个具体的类型值，该类型值具有接口所需的方法。或者换句话说，接口是方法的集合，也是自定义类型。想了解更多关于接口的内容，请参考《Golang 中的[接口一文](https://www.geeksforgeeks.org/interfaces-in-golang/)

有两个结构和一个接口。一种结构用于 gfg 课程细节，另一种结构用于竞赛细节。一个界面是 get_name 方法，它将返回课程和竞赛的名称。在接口的帮助下，我们将访问结构的变量，因为我们不想从外部访问结构的变量。

**示例 1:** 该程序将接受 2 个输入。

## Go

```go
// Golang program to access the interface fields
package main

import "fmt"

// Declare course structure
type Course struct {
    name string
}

// Declare contest structure
type Contest struct {
    name string
}

// Declare interface
type Name interface {
    get_name() string
}

// get_name function for course
func (a Course) get_name() string {

    return a.name

}

// get_name function for contest
func (b Contest) get_name() string {

    return b.name

}

// Compare course and contest name.
// Name is interface type
func name_compare(course, contest Name) bool {

    return contest.get_name() == course.get_name();

}

func main() {

    var course_name, contest_name string

    // Get the course name from user
    fmt.Println("Enter course name: ")
    fmt.Scan(&course_name)

    // Get the contest's name from user
    fmt.Println("Enter contest name: ")
    fmt.Scan(&contest_name)

    // Create structure of course
    course := Course{course_name}

    // Create structure of contest
    contest := Contest{contest_name}

    fmt.Print("Is same subjects in course and contest: ")

    // Call interface function to compare names
    fmt.Print(name_compare(course, contest))
}
```

**输出:**

```go
Enter course name: DBMS
Enter contest name: DBMS
Is same subjects in course and contest: true
```

**示例 2:** 该程序将接受 2 个输入。

## Go

```go
// Golang program to access the interface fields
package main

import "fmt"

// Declare courseprice structure
type Courseprice struct {
    price int
}

// Declare contestprice structure
type Couponprice struct {
    price int
}

// Declare interface
type Price interface {
    get_price() int
}

// get_price function for Courseprice
func (a Courseprice) get_price() int {

    return a.price

}

// get_price function for Coupon price
func (b Couponprice) get_price() int {

    return b.price

}

// Compare courseprice and Couponprice.
// Price is interface type
func price_compare(courseprice, Couponprice Price) bool {

    if courseprice.get_price() <= Couponprice.get_price() {

        return true

    } else {

        return false

    }

}

func main() {

    var courseprice, Couponprice int

    // Get the courseprice from user
    fmt.Println("Enter course price: ")
    fmt.Scan(&courseprice)

    // Get the Couponprice  from user
    fmt.Println("Enter Coupon Price: ")
    fmt.Scan(&Couponprice)

    // Create structure of courseprice
    course := Courseprice{courseprice}

    // Create structure of Couponprice
    Coupon := Couponprice{Couponprice}

    fmt.Print("Is the course is free: ")

    // Call interface function to compare price
    fmt.Print(price_compare(course, Coupon))
}
```

**输出:**

```go
Enter course price: 1000
Enter Coupon Price: 700
Is the course is free: false
```