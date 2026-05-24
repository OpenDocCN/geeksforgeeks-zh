# 如何替换 Golang 中字节片的所有元素？

> 原文:[https://www . geesforgeks . org/如何替换 golang 中字节片的所有元素/](https://www.geeksforgeeks.org/how-to-replace-all-the-elements-in-slice-of-bytes-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在字节的 Go 切片中，您可以使用 **ReplaceAll()** 函数替换给定切片中的所有元素。此函数用于用新切片替换旧切片的所有元素。如果给定的旧切片是空的，那么它在切片的开始匹配，并且在每个 UTF 8 序列之后，它产生多达 m+1 个 m 符文串的替换。它是在字节包下定义的，所以你必须在程序中导入字节包来访问 RepeatAll 函数。

**语法:**

```go
func ReplaceAll(ori_slice, old_slice, new_slice []byte) []byte
```

这里 *ori_slice* 是字节的原始切片， *old_slice* 是你要替换的切片， *new_slice* 是替换 *old_slice* 的新切片。

**例 1:**

```go
// Go program to illustrate how to replace all
// the specified elements of the slice of bytes
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
    slice_1 := []byte{'G', 'G', 'G', 'E',
       'E', 'E', 'E', 'K', 'S', 'S', 'S'}

    slice_2 := []byte{'A', 'A', 'P', 
           'P', 'P', 'L', 'E', 'E'}

    // Displaying slices
    fmt.Println("Original slice:")
    fmt.Printf("Slice 1: %s", slice_1)
    fmt.Printf("\nSlice 2: %s", slice_2)

    // Replacing the element 
    // of the given slices
    // Using ReplaceAll function
    res1 := bytes.ReplaceAll(slice_1, []byte("E"), []byte("e"))
    res2 := bytes.ReplaceAll(slice_2, []byte("P"), []byte("p"))

    // Display the results
    fmt.Printf("\n\nNew Slice:")
    fmt.Printf("\nSlice 1: %s", res1)
    fmt.Printf("\nSlice 2: %s", res2)
}
```

**输出:**

```go
Original slice:
Slice 1: GGGEEEEKSSS
Slice 2: AAPPPLEE

New Slice:
Slice 1: GGGeeeeKSSS
Slice 2: AApppLEE

```

**例 2:**

```go
// Go program to illustrate how to replace all
// the specified elements from the given
// slice of bytes
package main

import (
    "bytes"
    "fmt"
)

// Main function
func main() {

    // Replacing the element
    // of the given slices
    // Using ReplaceAll function
    res1 := bytes.ReplaceAll([]byte("GeeksforGeeks, Geeks, Geeks"), []byte("eks"), []byte("EKS"))
    res2 := bytes.ReplaceAll([]byte("Hello! i am Puppy, Puppy, Puppy"), []byte("upp"), []byte("ISL"))
    res3 := bytes.ReplaceAll([]byte("GFG, GFG, GFG"), []byte("GFG"), []byte("geeks"))
    res4 := bytes.ReplaceAll([]byte("I like like icecream"), []byte("like"), []byte("love"))

    // Display the results
    fmt.Printf("Result 1: %s", res1)
    fmt.Printf("\nResult 2: %s", res2)
    fmt.Printf("\nResult 3: %s", res3)
    fmt.Printf("\nResult 4: %s", res4)
}
```

**输出:**

```go
Result 1: GeEKSforGeEKS, GeEKS, GeEKS
Result 2: Hello! i am PISLy, PISLy, PISLy
Result 3: geeks, geeks, geeks
Result 4: I love love icecream

```