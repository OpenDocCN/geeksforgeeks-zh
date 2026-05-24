# 如何在 Golang 中使用 for 和 foreach 循环？

> 原文:[https://www . geeksforgeeks . org/golang 中的 for-for-foreach 循环使用方法/](https://www.geeksforgeeks.org/how-to-use-for-and-foreach-loop-in-golang/)

Golang 中只有一个循环构造，那就是循环的**。Golang 中的 for 循环有三个组件，必须用分号(；)，这些是:**

*   **初始化语句**:在第一次迭代之前执行。例如 i := 0
*   **条件表达式**:就在每次迭代之前执行。例如:i < 5
*   **Post 语句:**在每次迭代结束时执行。例如 i++

不需要任何**括号**来包含这三个组件，但是要定义一个块，我们必须使用括号 **{ }** 。

```go
for i := 0 ; i < 5 ; i++{
         // statements to execute......
}
```

***初始化和 post 语句是可选的。**T3】*

```go
i:=0
for ; i < 5;{
i++
}
```

您可以使用 ***作为 Golang 中的 while loop*** 。去掉所有的分号。

```go
i := 0
for i < 5 {
i++
}
```

**无限循环:**如果没有条件语句，则循环成为无限循环。

```go
for {
}
```

**例:**

## 去

```go
package main

import "fmt"

// function to print numbers 0
// to 9 and print the sum of 0 to 9
func main() {

    // variable to store the sum
    sum := 0

    // this is a for loop which runs from 0 to 9
    for i := 0; i < 10; i++ {

        // printing the value of
        // i : the iterating variable
        fmt.Printf("%d ", i)

        // calculating the sum
        sum += i
    }
    fmt.Printf("\nsum = %d", sum)
}
```

**输出:**

```go
0 1 2 3 4 5 6 7 8 9 
sum = 45
```

**在 Golang 没有 foreach 循环**，取而代之的是循环的**可以作为 **foreach** 。有一个关键字*范围*，可以将的*和*范围*组合在一起，在循环内可以选择使用*键*或*值*。***

**语法:**

```go
for <key>, <value> := range <container>{

}
```

在这里，

*   **键****值**:可以是你想选择的任意变量。
*   **容器**:可以是数组、列表、映射等任意变量。

**例 1:**

## 去

```go
package main

import "fmt"

// Driver function to show the
// use of for and range together
func main() {

    // here we used a map of integer to string
    mapp := map[int]string{1: "one", 2: "two", 3: "three"}

    // integ act as keys of mapp
    // spell act as the values of
    // mapp which is mapped to integ

    for integ, spell := range mapp {

        // using integ and spell as
        // key and value of the map
        fmt.Println(integ, " = ", spell)
    }
}
```

**输出:**

```go
1  =  one
2  =  two
3  =  three
```

**例 2:**

## 去

```go
package main

import "fmt"

// Driver function to show the
// use of for and range together
func main() {

    // declaring an array of integers
    arra := []int{1, 2, 3, 4}

    // traversing through the array
    for index, itr := range arra {

        // the key or value variables
        // used in for syntax
        // depends on the container.
        // If its an array or list,
        // the key refers to the index...
        fmt.Print(index, " : ", itr, "\n")
    }

    // if we use only one
    // variable in the for loop,
    // it by default refers to
    // the value in the container.
    for itr := range arra {

        fmt.Print(it, " ")
    }
}
```

**输出:**

```go
0 : 1
1 : 2
2 : 3
3 : 4
1 2 3 4 
```