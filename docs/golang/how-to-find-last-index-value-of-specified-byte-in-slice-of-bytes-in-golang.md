# 如何在 Golang 的字节片中找到指定字节的最后一个索引值？

> 原文:[https://www . geesforgeks . org/如何在 golang 字节片中查找指定字节的最后索引值/](https://www.geeksforgeeks.org/how-to-find-last-index-value-of-specified-byte-in-slice-of-bytes-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在字节的 Go 切片中，可以使用 **LastIndexByte()** 函数找到给定切片中指定字节的最后一个索引值。此函数返回给定字节片中指定字节的最后一个实例的索引。如果给定字节在原始切片中不可用，则该方法将返回 **-1** 。它是在字节包下定义的，所以您必须在程序中导入字节包来访问 LastIndexByte 函数。

**语法:**

```go
func LastIndexByte(ori_slice []byte, val byte) int
```

这里， **ori_slice** 是原始切片， **val** 是一个字节，我们要找到它的最后一个索引值。让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate the concept of
// the last index in the slice of bytes
package main

import (
    "bytes"
    "fmt"
)

func main() {

    // Creating and finding the last
    // index of the slice of bytes
    // Using LastIndexByte function
    res1 := bytes.LastIndexByte([]byte("****Welcome to GeeksforGeeks****"),
                                                                 byte('G'))

    res2 := bytes.LastIndexByte([]byte("Learning how to trim a slice of bytes"), 
                                                                     byte('e'))

    res3 := bytes.LastIndexByte([]byte("GeeksforGeeks, Geek"), byte('x'))

    // Display the results
    fmt.Printf("Final Value:\n")
    fmt.Printf("\nSlice 1: %d", res1)
    fmt.Printf("\nSlice 2: %d", res2)
    fmt.Printf("\nSlice 3: %d", res3)
}
```

**输出:**

```go
Final Value:

Slice 1: 23
Slice 2: 35
Slice 3: -1

```

**例 2:**

```go
// Go program to illustrate the concept of
// the last index in the slice of bytes
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
    fmt.Printf("Original Slice:\n\n")
    fmt.Printf("Slice 1: %s", slice_1)
    fmt.Printf("\nSlice 2: %s", slice_2)
    fmt.Printf("\nSlice 3: %s", slice_3)

    // Finding the last index of the slice of 
    // bytes Using LastIndexByte function
    res1 := bytes.LastIndexByte(slice_1, byte('e'))
    res2 := bytes.LastIndexByte(slice_2, byte('p'))
    res3 := bytes.LastIndexByte(slice_3, byte('w'))

    // Display the results
    fmt.Printf("\n\nLast Index:\n")
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

Last Index:

Slice 1: 12
Slice 2: 2
Slice 3: -1

```