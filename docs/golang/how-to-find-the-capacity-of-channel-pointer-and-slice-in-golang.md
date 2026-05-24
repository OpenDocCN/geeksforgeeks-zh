# 如何找到 Golang 中通道、指针、切片的容量？

> 原文:[https://www . geeksforgeeks . org/如何在 golang 中找到通道指针和切片的容量/](https://www.geeksforgeeks.org/how-to-find-the-capacity-of-channel-pointer-and-slice-in-golang/)

Go 语言，容量定义了一个特定的元素可以容纳的最大数量。这里的任务是在戈朗找到[通道](https://www.geeksforgeeks.org/channel-in-golang/)、[指针](https://www.geeksforgeeks.org/pointers-in-golang/)、[切片](https://www.geeksforgeeks.org/slices-in-golang/)的容量，我们可以使用 **cap()** 功能。

**语法:**

```go
func cap(l Type) int

```

这里，l 的类型是指针。

让我们借助例子来讨论这个概念:

**例 1:** 本例使用 cap()函数求 Golang 中 Pointer 的容量。

```go
// Go program to illustrate how to find the 
// capacity of the pointer 
package main 

import ( 
    "fmt"
) 

// Main function 
func main() { 

    // Creating and initializing 
    // pointer
    // Using var keyword 
    var ptr1 [7]*int
    var ptr2 [5]*string 
    var ptr3 [8]*float64 

    // Finding the capacity of 
    // the pointer
    // Using cap function 
    fmt.Println("Capacity of ptr1: ", cap(ptr1)) 
    fmt.Println("Capacity of ptr2: ", cap(ptr2)) 
    fmt.Println("Capacity of ptr3: ", cap(ptr3)) 

} 
```

**输出:**

```go
Capacity of ptr1:  7
Capacity of ptr2:  5
Capacity of ptr3:  8

```

**例 2:** 本例使用 cap()函数求 Golang 中 Channel 的容量。

```go
// Go program to illustrate how to find the 
// capacity of the Channel
package main 

import ( 
    "fmt"
) 

// Main function 
func main() { 

    // Creating and initializing 
    // Channel
    // Using var keyword 
    ch1 := make(chan int, 7) 
    ch2 := make(chan string, 5)
    ch3 := make(chan float64, 8)

    // Finding the capacity of 
    // the Channel
    // Using cap function 
    fmt.Println("Capacity of Channel1: ", cap(ch1)) 
    fmt.Println("Capacity of Channel2: ", cap(ch2)) 
    fmt.Println("Capacity of Channel3: ", cap(ch3)) 

} 
```

**输出:**

```go
Capacity of Channel1:  7
Capacity of Channel2:  5
Capacity of Channel3:  8

```

**例 3:** 在本例中，使用 cap()函数来查找 Golang 中 Slice 的容量。

```go
// Go program to illustrate how to find the 
// capacity of the Slice 
package main 

import ( 
    "fmt"
) 

// Main function 
func main() { 

    // Creating and initializing 
    // Slice 
    // Using var keyword 
    sl1 := make([]int, 0, 7) 
    sl2 := make([]string, 0, 5)
    sl3 := make([]float64, 0, 8)

    // Finding the capacity of 
    // the Slice 
    // Using cap function 
    fmt.Println("Capacity of Slice1: ", cap(sl1)) 
    fmt.Println("Capacity of Slice2: ", cap(sl2)) 
    fmt.Println("Capacity of Slice3: ", cap(sl3)) 

}
```

**输出:**

```go
Capacity of Slice1:  7
Capacity of Slice2:  5
Capacity of Slice3:  8

```