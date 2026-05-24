# 如何从 Golang 中的字节片修剪前缀？

> 原文:[https://www . geesforgeks . org/如何从 golang 中的字节片中修剪前缀/](https://www.geeksforgeeks.org/how-to-trim-prefix-from-the-slice-of-bytes-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在字节的 Go 切片中，您可以使用 **TrimPrefix()** 功能从给定切片中修剪前缀。这个函数通过切断给定的前导前缀字符串来返回原始切片的子切片。如果给定的字节片段不包含指定的前缀字符串，则此函数返回原始片段，不做任何更改。它是在字节包下定义的，所以您必须在程序中导入字节包来访问 TrimPrefix 函数。

**语法:**

```go
func TrimPrefix(ori_slice, pfx []byte) []byte
```

这里 *ori_slice* 是字节的原始切片，pfx 代表前缀。让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate the concept of
// trimming prefix in the slice of bytes
package main

import (
    "bytes"
    "fmt"
)

func main() {

    // Creating and trimming the slice of bytes
    // Using TrimPrefix function
    res1 := bytes.TrimPrefix([]byte("****Welcome to GeeksforGeeks****"), 
                                                          []byte("**"))

    res2 := bytes.TrimPrefix([]byte("Learning how to trim a slice of bytes"),
                                                            []byte("Learn"))

    res3 := bytes.TrimPrefix([]byte("GeeksforGeeks, Geek"), []byte("apple"))

    // Display the results
    fmt.Printf("\n\nFinal Slice:\n")
    fmt.Printf("\nSlice 1: %s", res1)
    fmt.Printf("\nSlice 2: %s", res2)
    fmt.Printf("\nSlice 3: %s", res3)
}
```

**输出:**

```go
Final Slice:

Slice 1: **Welcome to GeeksforGeeks****
Slice 2: ing how to trim a slice of bytes
Slice 3: GeeksforGeeks, Geek

```

**例 2:**

```go
// Go program to illustrate the concept
// of trimming prefix in the slice of bytes
package main

import (
    "bytes"
    "fmt"
)

func main() {

    // Creating and initializing the slice of bytes
    // Using shorthand declaration

    slice_1 := []byte{'!', '!', 'G', 'e', 'e', 'k', 's', 'f', 'o',
                       'r', 'G', 'e', 'e', 'k', 's', '#', '#'}
    slice_2 := []byte{'A', 'p', 'p', 'l', 'e'}
    slice_3 := []byte{'%', 'g', 'e', 'e', 'k', 's', '%'}

    // Displaying slices
    fmt.Println("Original Slice:")
    fmt.Printf("Slice 1: %s", slice_1)
    fmt.Printf("\nSlice 2: %s", slice_2)
    fmt.Printf("\nSlice 3: %s", slice_3)

    // Trimming specified prefix Unicodes
    // points from the given slice of bytes
    // Using TrimPrefix function
    res1 := bytes.TrimPrefix(slice_1, []byte("!!"))
    res2 := bytes.TrimPrefix(slice_2, []byte("A"))
    res3 := bytes.TrimPrefix(slice_3, []byte("as"))

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
Slice 2: Apple
Slice 3: %geeks%

New Slice:

Slice 1: GeeksforGeeks##
Slice 2: pple
Slice 3: %geeks%

```