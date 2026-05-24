# 戈朗的传承

> 原文:[https://www.geeksforgeeks.org/inheritance-in-golang/](https://www.geeksforgeeks.org/inheritance-in-golang/)

**继承**是指将超类的属性继承到基类中，是面向对象编程中最重要的概念之一。由于 Golang 不支持类，所以继承是通过结构嵌入实现的。我们不能直接扩展结构，而是使用一个叫做**合成**的概念，其中结构被用来形成其他对象。所以，你可以说戈朗 有*无继承观念。*

在组合中，基本结构可以嵌入到子结构中，并且基本结构的方法可以直接在子结构上调用，如下例所示。

**例 1:**

```go
// Golang program to illustrate the
// concept of inheritance
package main

import (
    "fmt"
)

// declaring a struct 
type Comic struct{

    // declaring struct variable
    Universe string
}

// function to return the
// universe of the comic
func (comic Comic) ComicUniverse() string {

    // returns comic universe
    return comic.Universe
}

// declaring a struct
type Marvel struct{

    // anonymous field,
    // this is composition where 
    // the struct is embedded
    Comic
}

// declaring a struct
type DC struct{

    // anonymous field
    Comic
}

// main function
func main() {

    // creating an instance
    c1 := Marvel{

        // child struct can directly
        // access base struct variables
            Comic{
            Universe: "MCU",
            },
        }

    // child struct can directly
    // access base struct methods

    // printing base method using child
        fmt.Println("Universe is:", c1.ComicUniverse())     

    c2 := DC{
        Comic{
            Universe : "DC",
        },
    }

    // printing base method using child
    fmt.Println("Universe is:", c2.ComicUniverse())
}
```

**输出:**

```go
Universe is: MCU
Universe is: DC

```

当子结构能够访问多个基本结构的多个属性、字段和方法时，就会发生多个继承。这里，子结构嵌入了所有的基本结构，如下面的代码所示:

**例 2:**

```go
// Golang program to illustrate the
// concept of multiple inheritances
package main

import (
    "fmt"
)

// declaring first 
// base struct 
type first struct{

    // declaring struct variable
    base_one string
}

// declaring second
// base struct
type second struct{

    // declaring struct variable
    base_two string
}

// function to return
// first struct variable
func (f first) printBase1() string{

    // returns a string
    // of first struct        
    return f.base_one
}

// function to return
// second struct variable
func (s second) printBase2() string{

    // returns a string
    // of first struct
    return s.base_two
}

// child struct which
// embeds both base structs
type child struct{

    // anonymous fields,
    // struct embedding
    // of multiple structs
    first
    second
}

// main function
func main() {

    // declaring an instance 
    // of child struct
    c1 := child{

        // child struct can directly
        // access base struct variables
        first{    
            base_one: "In base struct 1.",
        },
        second{
            base_two: "\nIn base struct 2.\n",
        },
    }

    // child struct can directly
    // access base struct methods

    // printing base method
    // using instance of child struct
    fmt.Println(c1.printBase1())
    fmt.Println(c1.printBase2())
}
```

**输出:**

```go
In base struct 1.

In base struct 2.

```