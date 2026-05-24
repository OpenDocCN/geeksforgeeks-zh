# 如何在 Golang 中找到指针的长度？

> 原文:[https://www . geesforgeks . org/如何找到 golang 中的指针长度/](https://www.geeksforgeeks.org/how-to-find-the-length-of-the-pointer-in-golang/)

[指针](https://www.geeksforgeeks.org/pointers-in-golang/)在 Go 编程语言或 Golang 中是一个变量，用来存储另一个变量的内存地址。Golang 中的指针也被称为特殊变量。变量用于在系统的特定内存地址存储一些数据。内存地址总是以十六进制格式出现(从 0x 开始，如 0xFFAAF 等)。).
在指针中，可以借助 **len()** 函数找到指针的长度。此函数是一个内置函数，即使指定的指针为零，它也会返回指向数组的指针中存在的元素总数。该功能在内置下定义。

**语法:**

```go
func len(l Type) int
```

这里 **l** 的类型是指针。让我们借助给定的例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how to find the
// length of the pointer to an array
package main

import (
    "fmt"
)

// Main function
func main() {

    // Creating and initializing
    // pointer to array
    // Using var keyword
    var ptr1 [6]*int
    var ptr2 [3]*string
    var ptr3 [4]*float64

    // Finding the length of 
    // the pointer to array
    // Using len function
    fmt.Println("Length of ptr1: ", len(ptr1))
    fmt.Println("Length of ptr2: ", len(ptr2))
    fmt.Println("Length of ptr3: ", len(ptr3))

}
```

**输出:**

```go
Length of ptr1:  6
Length of ptr2:  3
Length of ptr3:  4

```

**例 2:**

```go
// Go program to illustrate how to find
// the length of the pointer to an array
package main

import (
    "fmt"
)

// Main function
func main() {

    // Creating an array
    arr := [6]int{200, 300,
        400, 500, 600, 700}

    var x int

    // Creating pointer
    var p [4]*int

    // Assigning the address
    for x = 0; x < len(p); x++ {

        p[x] = &arr[x]
    }

    // Displaying result
    for x = 0; x < len(p); x++ {

        fmt.Printf("Value of p[%d] = %d\n", x, *p[x])
    }

    // Finding length
    // Using len() function
    fmt.Println("Length of arr: ", len(arr))
    fmt.Println("Length of p: ", len(p))
}
```

**输出:**

```go
Value of p[0] = 200
Value of p[1] = 300
Value of p[2] = 400
Value of p[3] = 500
Length of arr:  6
Length of p:  4

```