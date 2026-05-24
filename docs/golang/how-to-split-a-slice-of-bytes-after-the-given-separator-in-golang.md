# 如何在 Golang 中给定分隔符后拆分一片字节？

> 原文:[https://www . geeksforgeeks . org/如何在 golang 中给定分隔符后分割字节片/](https://www.geeksforgeeks.org/how-to-split-a-slice-of-bytes-after-the-given-separator-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在字节的 Go 切片中，您可以使用 *SplitAfter()* 函数在指定的分隔符后分割切片。该函数在给定分隔符的每个实例之后将一个字节片分割成所有子片，并返回一个包含这些子片的片。它是在字节包下定义的，所以你必须在程序中导入字节包来访问 SplitAfter 函数。

**语法:**

```go
func SplitAfter(o_slice, sep []byte) [][]byte
```

这里， *o_slice* 是字节的切片，sep 是分隔符。如果 *sep* 是空的，那么它将在每个 UTF-8 序列之后分裂。让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate the concept
// of splitting a slice of bytes
package main

import (
    "bytes"
    "fmt"
)

func main() {

    // Creating and Splitting 
    // the slice of bytes
    // Using SplitAfter function
    res1 := bytes.SplitAfter([]byte("****Welcome, to, GeeksforGeeks****"),
                                                             []byte(","))

    res2 := bytes.SplitAfter([]byte("Learning x how x to x trim x a x slice of bytes"),
                                                                          []byte("x"))

    res3 := bytes.SplitAfter([]byte("GeeksforGeeks, Geek"), []byte(""))

    res4 := bytes.SplitAfter([]byte(""), []byte(","))

    // Display the results
    fmt.Printf("\nFinal Result after splitting:\n")
    fmt.Printf("\nSlice 1: %s", res1)
    fmt.Printf("\nSlice 2: %s", res2)
    fmt.Printf("\nSlice 3: %s", res3)
    fmt.Printf("\nSlice 4: %s", res4)
}
```

**输出:**

```go
Final Result after splitting:

Slice 1: [****Welcome,  to,  GeeksforGeeks****]
Slice 2: [Learning x  how x  to x  trim x  a x  slice of bytes]
Slice 3: [G e e k s f o r G e e k s ,   G e e k]
Slice 4: []

```

**例 2:**

```go
// Go program to illustrate the concept
// of splitting a slice of bytes
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

    slice_3 := []byte{'%', 'g', '%', 'e', '%', 
                 'e', '%', 'k', '%', 's', '%'}

    // Displaying slices
    fmt.Println("Original Slice:")
    fmt.Printf("Slice 1: %s", slice_1)
    fmt.Printf("\nSlice 2: %s", slice_2)
    fmt.Printf("\nSlice 3: %s", slice_3)

    // Splitting the slice of bytes
    // Using SplitAfter function
    res1 := bytes.SplitAfter(slice_1, []byte("eek"))
    res2 := bytes.SplitAfter(slice_2, []byte(""))
    res3 := bytes.SplitAfter(slice_3, []byte("%"))

    // Display the results
    fmt.Printf("\n\nAfter splitting:\n")
    fmt.Printf("\nSlice 1: %s", res1)
    fmt.Printf("\nSlice 2: %s", res2)
    fmt.Printf("\nSlice 3: %s", res3)

}
```

**输出:**

```go
Original Slice:
Slice 1: !!GeeksforGeeks##
Slice 2: Apple
Slice 3: %g%e%e%k%s%

After splitting:

Slice 1: [!!Geek sforGeek s##]
Slice 2: [A p p l e]
Slice 3: [% g% e% e% k% s% ]

```