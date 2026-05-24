# 如何在 Golang 中找到字节片的第一个索引值？

> 原文:[https://www . geesforgeks . org/如何在 golang 中找到第一个字节片索引值/](https://www.geeksforgeeks.org/how-to-find-the-first-index-value-in-slice-of-bytes-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在字节的 Go 切片中，可以使用 **Index()** 函数找到给定切片中指定实例的第一个索引值。此函数返回给定值在原始字节片中的第一个实例的索引。如果原始切片中没有给定值，则返回 *-1* 。它是在字节包下定义的，所以您必须在程序中导入字节包来访问索引函数。

**语法:**

```go
func Index(ori_slice, sep_ []byte) int
```

这里 *ori_slice* 是原始切片， *sep_* 是一个切片，我们要找到它的第一个索引值。让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate the concept
// of the index in the slice of bytes
package main

import (
    "bytes"
    "fmt"
)

func main() {

    // Creating and finding the index 
    // of the slice of bytes
    // Using Index function
    res1 := bytes.Index([]byte("****Welcome to GeeksforGeeks****"), 
                                                    []byte("eek"))

    res2 := bytes.Index([]byte("Learning how to trim a slice of bytes"),
                                                          []byte("xzx"))

    res3 := bytes.Index([]byte("GeeksforGeeks, Geek"), []byte("eeks"))

    // Display the results
    fmt.Printf("\n\nFinal Value:\n")
    fmt.Printf("\nSlice 1: %d", res1)
    fmt.Printf("\nSlice 2: %d", res2)
    fmt.Printf("\nSlice 3: %d", res3)
}
```

**输出:**

```go
Final Value:

Slice 1: 16
Slice 2: -1
Slice 3: 1

```

**例 2:**

```go
// Go program to illustrate the concept of
// the index in the slice of bytes
package main

import (
    "bytes"
    "fmt"
)

func main() {

    // Creating and initializing 
    // the slice of bytes
    // Using shorthand declaration
    slice_1 := []byte{'!', '!', 'G', 'e', 'e', 'k', 's', 
      'f', 'o', 'r', 'G', 'e', 'e', 'k', 's', '#', '#'}

    slice_2 := []byte{'A', 'p', 'p', 'l', 'e'}

    slice_3 := []byte{'%', 'g', 'e', 'e', 'k', 's', '%'}

    // Displaying slices
    fmt.Println("Original Slice:")
    fmt.Printf("Slice 1: %s", slice_1)
    fmt.Printf("\nSlice 2: %s", slice_2)
    fmt.Printf("\nSlice 3: %s", slice_3)

    // Finding the index of
    // the slice of bytes
    // Using Index function
    res1 := bytes.Index(slice_1, []byte("eek"))
    res2 := bytes.Index(slice_2, []byte("ple"))
    res3 := bytes.Index(slice_3, []byte("xox"))

    // Display the results
    fmt.Printf("\n\nFirst Index:\n")
    fmt.Printf("\nSlice 1: %d", res1)
    fmt.Printf("\nSlice 2: %d", res2)
    fmt.Printf("\nSlice 3: %d", res3)

}
```

**输出:**

```go
Original Slice:
Slice 1: !!GeeksforGeeks##
Slice 2: Apple
Slice 3: %geeks%

First Index:

Slice 1: 3
Slice 2: 2
Slice 3: -1

```