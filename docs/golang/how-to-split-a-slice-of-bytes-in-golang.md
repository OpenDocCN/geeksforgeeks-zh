# 如何在 Golang 中拆分一片字节？

> 原文:[https://www . geeksforgeeks . org/如何分割 golang 中的字节片/](https://www.geeksforgeeks.org/how-to-split-a-slice-of-bytes-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在字节的 Go 切片中，您可以使用**分割()**功能分割给定的切片。该函数将一个字节片分割成由给定分隔符分隔的所有子片，并返回一个包含所有这些子片的片。它是在字节包下定义的，所以您必须在程序中导入字节包来访问分割函数。

**语法:**

```go
func Split(o_slice, sep []byte) [][]byte
```

这里， *o_slice* 是字节的切片， *sep* 是分隔符。如果 *sep* 是空的，那么它将在每个 UTF-8 序列之后分裂。让我们借助给定的例子来讨论这个概念:

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

    // Creating and initializing
    // the slice of bytes
    // Using shorthand declaration
    slice_1 := []byte{'!', '!', 'G', 'e', 'e', 'k', 's', 
       'f', 'o', 'r', 'G', 'e', 'e', 'k', 's', '#', '#'}

    slice_2 := []byte{'A', 'p', 'p', 'l', 'e'}

    slice_3 := []byte{'%', 'g', '%', 'e', '%', 'e', 
                           '%', 'k', '%', 's', '%'}

    // Displaying slices
    fmt.Println("Original Slice:")
    fmt.Printf("Slice 1: %s", slice_1)
    fmt.Printf("\nSlice 2: %s", slice_2)
    fmt.Printf("\nSlice 3: %s", slice_3)

    // Splitting the slice of bytes
    // Using Split function
    res1 := bytes.Split(slice_1, []byte("eek"))
    res2 := bytes.Split(slice_2, []byte(""))
    res3 := bytes.Split(slice_3, []byte("%"))

    // Display the results
    fmt.Printf("\n\nAfter splitting:")
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
Slice 1: [!!G sforG s##]
Slice 2: [A p p l e]
Slice 3: [ g e e k s ]

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

    // Creating and Splitting
    // the slice of bytes
    // Using Split function
    res1 := bytes.Split([]byte("****Welcome, to, GeeksforGeeks****"), 
                                                         []byte(","))

    res2 := bytes.Split([]byte("Learning x how x to x trim x a x slice of bytes"),
                                                                     []byte("x"))

    res3 := bytes.Split([]byte("GeeksforGeeks, Geek"), []byte(""))

    res4 := bytes.Split([]byte(""), []byte(","))

    // Display the results
    fmt.Printf("Final Value:\n")
    fmt.Printf("\nSlice 1: %s", res1)
    fmt.Printf("\nSlice 2: %s", res2)
    fmt.Printf("\nSlice 3: %s", res3)
    fmt.Printf("\nSlice 4: %s", res4)
}
```

**输出:**

```go
Final Value:

Slice 1: [****Welcome  to  GeeksforGeeks****]
Slice 2: [Learning   how   to   trim   a   slice of bytes]
Slice 3: [G e e k s f o r G e e k s ,   G e e k]
Slice 4: []

```