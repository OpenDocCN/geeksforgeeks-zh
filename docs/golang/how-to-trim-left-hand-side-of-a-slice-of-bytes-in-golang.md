# 如何在 Golang 中修剪一片字节的左侧？

> 原文:[https://www . geeksforgeeks . org/如何修剪 golang 中的字节片左侧/](https://www.geeksforgeeks.org/how-to-trim-left-hand-side-of-a-slice-of-bytes-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在字节的 Go 切片中，您可以使用 **TrimLeft()** 功能从给定切片中修剪所有 UTF-8 编码的起始码点。这个函数通过切掉给定字符串中指定的所有 UTF 8 编码码点，返回原始切片的子切片。如果给定的字节片段在其左侧不包含指定的字符串，则此函数返回原始片段，不做任何更改。它是在字节包下定义的，所以你必须在你的程序中导入字节包来访问 TrimLeft 函数。

**语法:**

```go
func TrimLeft(ori_slice[]byte, cut_string string) []byte
```

这里， *ori_slice* 是字节的原始切片， *cut_string* 代表要在给定切片中修剪的字符串。让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate the concept
// of left trim in the slice of bytes
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

    slice_2 := []byte{'*', '*', 'A', 'p', 'p', 'l', 'e', '^', '^'}

    slice_3 := []byte{'%', 'g', 'e', 'e', 'k', 's', '%'}

    // Displaying slices
    fmt.Println("Original Slice:")
    fmt.Printf("Slice 1: %s", slice_1)
    fmt.Printf("\nSlice 2: %s", slice_2)
    fmt.Printf("\nSlice 3: %s", slice_3)

    // Trimming specified leading Unicodes 
    // points from the given slice
    // Using TrimLeft function
    res1 := bytes.TrimLeft(slice_1, "!#")
    res2 := bytes.TrimLeft(slice_2, "*")
    res3 := bytes.TrimLeft(slice_3, "@")

    // Display the results
    fmt.Printf("\n\nNew Slice:\n")
    fmt.Printf("\nSlice 1: %s", res1)
    fmt.Printf("\nSlice 2: %s", res2)
    fmt.Printf("\nSlice 3: %s", res3)

}
```

**输出:**

```go
Original Slice:
Slice 1: !!GeeksforGeeks##
Slice 2: **Apple^^
Slice 3: %geeks%

New Slice:

Slice 1: GeeksforGeeks##
Slice 2: Apple^^
Slice 3: %geeks%

```

**例 2:**

```go
// Go program to illustrate the concept
// of left trim in the slice of bytes
package main

import (
    "bytes"
    "fmt"
)

func main() {

    // Creating and trimming
    // the slice of bytes
    // Using TrimLeft function
    res1 := bytes.TrimLeft([]byte("****Welcome to GeeksforGeeks****"), "*")
    res2 := bytes.TrimLeft([]byte("!!!!Learning how to trim a slice of bytes@@@@"), "!@")
    res3 := bytes.TrimLeft([]byte("^^Geek&&"), "{content}quot;)

    // Display the results
    fmt.Printf("\nFinal Slice:\n")
    fmt.Printf("\nSlice 1: %s", res1)
    fmt.Printf("\nSlice 2: %s", res2)
    fmt.Printf("\nSlice 3: %s", res3)
}
```

**输出:**

```go
Final Slice:

Slice 1: Welcome to GeeksforGeeks****
Slice 2: Learning how to trim a slice of bytes@@@@
Slice 3: ^^Geek&&

```