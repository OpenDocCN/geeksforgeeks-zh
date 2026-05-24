# 如何在 Golang 中使用值和指针引用复制结构类型？

> 原文:[https://www . geeksforgeeks . org/如何复制结构类型使用值和指针引用在 golang/](https://www.geeksforgeeks.org/how-to-copy-struct-type-using-value-and-pointer-reference-in-golang/)

Golang 中的结构或**结构**是用户定义的数据类型，允许组合不同种类的数据类型并作为记录。
使用**赋值语句(=)** ，可以很容易地将 Golang 中的一个结构变量复制到另一个变量中。对第二个结构所做的任何更改都不会反映回第一个结构。

**例 1:**

```go
// Golang program to illustrate copying
// a structure to another variable

package main

import (
    "fmt"
)

// declaring a structure
type Student struct{

    // declaring variables
    name string
    marks int64
    stdid int64
}

// main function
func main() {

    // creating the instance of the 
    // Student struct type 
    std1 := Student{"Vani", 98, 20024}

    // prints the student struct
    fmt.Println(std1)

    // copying the struct student
    // to another variable by 
    // using the assignment operator
    std2 := std1

    // printing copied struct
    // this will have same values 
    // as struct std1
    fmt.Println(std2)

    // changing values of struct
    // std2 after copying
    std2.name = "Abc"
    std2.stdid = 20025

    // printing updated struct
    fmt.Println(std2)

}
```

**输出:**

```go
{Vani 98 20024}
{Vani 98 20024}
{Abc 98 20025}

```

在指针引用结构的情况下，原始结构的底层内存位置和指向该结构的指针将是相同的。对第二个结构所做的任何更改也会反映在第一个结构中。指向一个结构的指针是通过使用**和运算符(& )** 来实现的。它是在堆上分配的，它的地址是共享的。

**例 2:**

```go
// Golang program to illustrate the
// concept of a pointer to a struct

package main

import (
    "fmt"
)

// declaring a structure
type Person struct{

    // declaring variables
    name string
    address string
    id int64
}

// main function
func main() {

    // creating the instance of the 
        // Person struct type 
    p1 := Person{"Vani", "Delhi", 20024}

    // prints the student struct
    fmt.Println(p1)

    // referencing the struct person
    // to another variable by 
    // using the ampersand operator
    // Here, it is the pointer to the struct 
    p2 := &p1

    // printing pointer to the struct
    fmt.Println(p2)

    // changing values of struct p2
    p2.name = "Abc"
    p2.address = "Hyderabad"

    // printing updated struct
    fmt.Println(p2)

    // struct p1 values will 
    // also change since values
    // of p2 were also changed
    fmt.Println(p1)

}
```

**输出:**

```go
{Vani Delhi 20024}
&{Vani Delhi 20024}
&{Abc Hyderabad 20024}
{Abc Hyderabad 20024}

```