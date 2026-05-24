# 如何在 Golang 中替换字节片中的指定元素？

> 原文:[https://www . geesforgeks . org/如何替换指定的 golang 字节片元素/](https://www.geeksforgeeks.org/how-to-replace-a-specified-element-in-slice-of-bytes-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在字节的 Go 切片中，您可以使用 **Replace()** 函数替换给定切片中的指定元素。此函数返回包含新切片的切片副本，该切片是通过替换旧切片中的元素而创建的。如果给定的旧切片是空的，那么它在切片的开始匹配，并且在每个 UTF-8 序列之后，它产生高达 *m+1* 的 m-符文切片替换。如果 m 的值小于零，那么这个函数可以替换给定切片中的任意数量的元素(没有任何限制)。它是在字节包下定义的，所以你必须在程序中导入字节包来访问重复函数。

**语法:**

```go
func Replace(ori_slice, old_slice, new_slice []byte, m int) []byte
```

这里 *ori_slice* 是字节的原始切片， *old_slice* 是你要替换的切片，new_slice 是替换 *old_slice* 的新切片，m 是 *old_slice* 替换的次数。

**例 1:**

```go
// Go program to illustrate how to replace
// the element of the slice of bytes
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

    // Displaying slices
    fmt.Println("Original slice:")
    fmt.Printf("Slice 1: %s", slice_1)
    fmt.Printf("\nSlice 2: %s", slice_2)

    // Replacing the element
    // of the given slices
    // Using Replace function
    res1 := bytes.Replace(slice_1, []byte("E"), []byte("e"), 2)
    res2 := bytes.Replace(slice_2, []byte("P"), []byte("p"), 1)

    // Display the results
    fmt.Printf("\n\nNew Slice:")
    fmt.Printf("\nSlice 1: %s", res1)
    fmt.Printf("\nSlice 2: %s", res2)
}
```

**输出:**

```go
Original slice:
Slice 1: GEEKS
Slice 2: APPLE

New Slice:
Slice 1: GeeKS
Slice 2: ApPLE

```

**例 2:**

```go
// Go program to illustrate how to replace
// the specified element from the given
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
    // Using Replace function
    res1 := bytes.Replace([]byte("GeeksforGeeks, Geeks, Geeks"), []byte("eks"), []byte("EKS"), 3)

    res2 := bytes.Replace([]byte("Hello! i am Puppy, Puppy, Puppy"), []byte("upp"), []byte("ISL"), 2)

    res3 := bytes.Replace([]byte("GFG, GFG, GFG"), []byte("GFG"), []byte("geeks"), -1)

    res4 := bytes.Replace([]byte("I like icecream"), []byte("like"), []byte("love"), 0)

    // Display the results
    fmt.Printf("Result 1: %s", res1)
    fmt.Printf("\nResult 2: %s", res2)
    fmt.Printf("\nResult 3: %s", res3)
    fmt.Printf("\nResult 4: %s", res4)
}
```

**输出:**

```go
Result 1: GeEKSforGeEKS, GeEKS, Geeks
Result 2:Hello! i am PISLy, PISLy, Puppy
Result 3:geeks, geeks, geeks
Result 4:I like icecream

```