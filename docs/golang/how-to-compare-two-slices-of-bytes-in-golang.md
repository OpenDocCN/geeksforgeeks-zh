# 如何比较 Golang 中的两片字节？

> 原文:[https://www . geesforgeks . org/如何比较两个字节片/golang/](https://www.geeksforgeeks.org/how-to-compare-two-slices-of-bytes-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。在 Go 切片中，您可以使用**比较()**功能将字节类型的两个切片相互比较。此函数返回一个整数值，表示这些切片是否相等，值为:

*   如果结果为 0，则 slice_1 == slice_2。
*   如果结果为-1，则 slice_1 < slice_2。
*   如果结果为+1，则 slice_1 > slice_2。

这个函数是在字节包下定义的，所以你必须在程序中导入字节包来访问比较函数。

**语法:**

```go
func Compare(slice_1, slice_2 []byte) int
```

让我们借助例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate how to
// compare two slices of bytes
package main

import (
    "bytes"
    "fmt"
)

// Main function
func main() {

    // Creating and initializing
    // slices of bytes
    // Using shorthand declaration

    slice_1 := []byte{'G', 'E', 'E', 'K', 'S'}
    slice_2 := []byte{'G', 'E', 'e', 'K', 'S'}

    // Comparing slice
    // Using Compare function
    res := bytes.Compare(slice_1, slice_2)

    if res == 0 {
        fmt.Println("!..Slices are equal..!")
    } else {
        fmt.Println("!..Slice are not equal..!")
    }
}
```

**输出:**

```go
!..Slice are not equal..!
```

**例 2:**

```go
// Go program to illustrate how
// to compare two slices of byte
package main

import (
    "bytes"
    "fmt"
)

func main() {

    // Creating and initializing
    // slices of bytes
    // Using shorthand declaration
    slice_1 := []byte{'A', 'N', 'M', 'O', 'P', 'Q'}
    slice_2 := []byte{'a', 'g', 't', 'e', 'q', 'm'}
    slice_3 := []byte{'A', 'N', 'M', 'O', 'P', 'Q'}
    slice_4 := []byte{'A', 'n', 'M', 'o', 'p', 'Q'}

    // Displaying slices
    fmt.Println("Slice 1: ", slice_1)
    fmt.Println("Slice 2: ", slice_2)
    fmt.Println("Slice 3: ", slice_3)
    fmt.Println("Slice 4: ", slice_4)

    // Comparing slices
    // Using Compare function
    res1 := bytes.Compare(slice_1, slice_2)
    res2 := bytes.Compare(slice_1, slice_3)
    res3 := bytes.Compare(slice_1, slice_4)
    res4 := bytes.Compare(slice_2, slice_3)
    res5 := bytes.Compare(slice_2, slice_4)
    res6 := bytes.Compare(slice_2, slice_1)
    res7 := bytes.Compare(slice_3, slice_1)
    res8 := bytes.Compare(slice_3, slice_2)
    res9 := bytes.Compare(slice_3, slice_4)
    res10 := bytes.Compare(slice_4, slice_1)
    res11 := bytes.Compare(slice_4, slice_2)
    res12 := bytes.Compare(slice_4, slice_3)
    res13 := bytes.Compare(slice_4, slice_4)

    // Displaying results
    fmt.Println("\nResult 1:", res1)
    fmt.Println("Result 2:", res2)
    fmt.Println("Result 3:", res3)
    fmt.Println("Result 4:", res4)
    fmt.Println("Result 5:", res5)
    fmt.Println("Result 6:", res6)
    fmt.Println("Result 7:", res7)
    fmt.Println("Result 8:", res8)
    fmt.Println("Result 9:", res9)
    fmt.Println("Result 10:", res10)
    fmt.Println("Result 11:", res11)
    fmt.Println("Result 12:", res12)
    fmt.Println("Result 13:", res13)
}
```

**输出:**

```go
Slice 1:  [65 78 77 79 80 81]
Slice 2:  [97 103 116 101 113 109]
Slice 3:  [65 78 77 79 80 81]
Slice 4:  [65 110 77 111 112 81]

Result 1: -1
Result 2: 0
Result 3: -1
Result 4: 1
Result 5: 1
Result 6: 1
Result 7: 0
Result 8: -1
Result 9: -1
Result 10: 1
Result 11: -1
Result 12: 1
Result 13: 0

```