# 如何在 Golang 中转换一片小写的字节？

> 原文:[https://www . geesforgeks . org/如何转换 golang 中的小写字节片/](https://www.geeksforgeeks.org/how-to-convert-a-slice-of-bytes-in-lowercase-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在 Go 切片字节中，您可以使用 *ToLower()* 函数转换小写切片。此函数返回给定字节片的副本(视为 UTF 8 编码字节)，其中所有 Unicode 字母都映射为小写。它是在字节包下定义的，所以您必须在程序中导入字节包来访问 ToLower 函数。

**语法:**

```go
func ToLower(slice_1 []byte) []byte
```

这里，slice_1 表示要转换为小写的字节片。

**示例:**

```go
// Go program to illustrate how to convert
// the case of the given slice into lowercase
package main

import (
    "bytes"
    "fmt"
)

// Main function
func main() {

    // Creating and initializing 
    // the slice of bytes
    // Using shorthand declaration
    slice_1 := []byte{'G', 'E', 'E', 'K', 'S'}
    slice_2 := []byte{'A', 'P', 'P', 'L', 'E'}

    //Displaying slices
    fmt.Println("Original slice:")
    fmt.Printf("Slice 1: %s", slice_1)
    fmt.Printf("\nSlice 2: %s", slice_2)

    // Converting the elements of the
    // given slices into lowercase
    // Using ToLower function
    res1 := bytes.ToLower(slice_1)
    res2 := bytes.ToLower(slice_2)
    res3 := bytes.ToLower([]byte("GEEKSFORGEEKS"))
    res4 := bytes.ToLower([]byte("GeeKSFORGeeKS"))

    // Display the results
    fmt.Printf("\n\nNew Slice:")
    fmt.Printf("\nSlice 1: %s", res1)
    fmt.Printf("\nSlice 2: %s", res2)
    fmt.Printf("\nSlice 3: %s", res3)
    fmt.Printf("\nSlice 4: %s", res4)
}
```

**输出:**

```go
Original slice:
Slice 1: GEEKS
Slice 2: APPLE

New Slice:
Slice 1: geeks
Slice 2: apple
Slice 3: geeksforgeeks
Slice 4: geeksforgeeks

```