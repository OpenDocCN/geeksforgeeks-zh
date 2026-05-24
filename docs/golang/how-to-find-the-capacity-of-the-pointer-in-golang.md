# 如何在 Golang 中找到指针的容量？

> 原文:[https://www . geesforgeks . org/如何找到 golang 中指针的容量/](https://www.geeksforgeeks.org/how-to-find-the-capacity-of-the-pointer-in-golang/)

[指针](https://www.geeksforgeeks.org/pointers-in-golang/)在 Go 编程语言或 Golang 中是一个变量，用来存储另一个变量的内存地址。Golang 中的指针也被称为特殊变量。变量用于在系统的特定内存地址存储一些数据。内存地址总是以十六进制格式出现(从 0x 开始，如 0xFFAAF 等)。).
在指针中，可以借助 **cap()** 函数找到指针的容量。这个函数是一个内置函数，返回数组指针的容量。在 Go 语言中，容量定义了数组指针中存储的最大元素数。该功能在内置下定义。

**语法:**

```go
func cap(l Type) int
```

这里 **l** 的类型是指针。让我们借助例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how to find the
// capacity of the pointer to an array
package main

import (
    "fmt"
)

// Main function
func main() {

    // Creating and initializing
    // pointer to array
    // Using var keyword
    var ptr1 [7]*int
    var ptr2 [5]*string
    var ptr3 [8]*float64

    // Finding the capacity of
    // the pointer to array
    // Using cap function
    fmt.Println("Capacity of ptr1: ", cap(ptr1))
    fmt.Println("Capacity of ptr2: ", cap(ptr2))
    fmt.Println("Capacity of ptr3: ", cap(ptr3))

}
```

**输出:**

```go
Capacity of ptr1 : 7
Capacity of ptr2 : 5
Capacity of ptr3 : 8

```

**例 2:**

```go
// Go program to illustrate how to find the
// capacity of the pointer to an array
package main

import (
    "fmt"
)

// Main function
func main() {

    // Creating an array
    arr := [8]int{200, 300, 400,
       500, 600, 700, 100, 200}

    var x int

    // Creating pointer
    var p [5]*int

    // Assigning the address
    for x = 0; x < len(p); x++ {
        p[x] = &arr[x]
    }

    // Displaying result
    for x = 0; x < len(p); x++ {

        fmt.Printf("Value of p[%d] = %d\n",
                                 x, *p[x])
    }

    // Finding capacity
    // using cap() function
    fmt.Println("Capacity of arr: ", cap(arr))
    fmt.Println("Capacity of p: ", cap(p))
}
```

**输出:**

```go
Value of p[0] = 200
Value of p[1] = 300
Value of p[2] = 400
Value of p[3] = 500
Value of p[4] = 600
Capacity of arr:  8
Capacity of p:  5

```