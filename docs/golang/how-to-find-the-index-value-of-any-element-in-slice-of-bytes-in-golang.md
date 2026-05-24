# 如何在 Golang 中找到字节片内任意元素的索引值？

> 原文:[https://www . geesforgeks . org/如何在 golang 中找到字节片中任何元素的索引值/](https://www.geeksforgeeks.org/how-to-find-the-index-value-of-any-element-in-slice-of-bytes-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在字节的 Go 切片中，可以使用 **IndexAny()** 函数找到给定切片中任何指定实例的第一个索引值。此函数返回字符中任何 Unicode 代码点的原始片段中第一次出现的字节索引。如果字符的 Unicode 代码点在原始切片中不可用或为空，则此方法将返回-1。它是在字节包下定义的，所以您必须在程序中导入字节包来访问索引任何函数。

**语法:**

```go
func IndexAny(ori_slice []byte, val string) int
```

这里， *ori_slice* 是原始字符串， *val* 是字符串，我们要找到它的第一个索引值。让我们借助给定的例子来讨论这个概念:

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
    // Using IndexAny function
    res1 := bytes.IndexAny([]byte("****Welcome to GeeksforGeeks****"),
                                                              "Gjskf")

    res2 := bytes.IndexAny([]byte("Learning how to trim a slice of bytes"),
                                                                   "qoxz")

    res3 := bytes.IndexAny([]byte("GeeksforGeeks, Geek"), 
                                                "HELLO")

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

Slice 1: 15
Slice 2: 10
Slice 3: -1

```

**例 2:**

```go
// Go program to illustrate the concept
// of the index in the slice of bytes
package main

import (
    "bytes"
    "fmt"
)

func main() {

    // Creating and initializing 
    // the slice of bytes
    // Using shorthand declaration
    slice_1 := []byte{'!', '!', 'G', 'e', 'e', 'k', 's', 'f', 
                 'o', 'r', 'G', 'e', 'e', 'k', 's', '#', '#'}

    slice_2 := []byte{'A', 'p', 'p', 'l', 'e'}

    slice_3 := []byte{'%', 'g', 'e', 'e', 'k', 's', '%'}

    // Displaying slices
    fmt.Println("Original Slice:")
    fmt.Printf("Slice 1: %s", slice_1)
    fmt.Printf("\nSlice 2: %s", slice_2)
    fmt.Printf("\nSlice 3: %s", slice_3)

    // Finding the index of
    // the slice of bytes
    // Using IndexAny function
    res1 := bytes.IndexAny(slice_1, "eks")
    res2 := bytes.IndexAny(slice_2, "lqzxm")
    res3 := bytes.IndexAny(slice_3, "xxxxx")

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

Slice 1: 3
Slice 2: 3
Slice 3: -1

```