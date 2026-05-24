# 如何统计戈朗切片中存在的特定字符？

> 原文:[https://www . geeksforgeeks . org/如何计数特定字符-在 golang 切片中出现/](https://www.geeksforgeeks.org/how-to-count-specific-characters-present-in-the-slice-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在 Go 切片字节中，可以借助*计数*功能对其中存在的元素进行计数。此函数返回给定切片中可用元素的总数或某些指定元素的总数。这个函数是在字节包下定义的，所以你必须在程序中导入字节包来访问计数函数。

**语法:**

```go
func Count(slice_1, sep_slice []byte) int
```

如果 *sep_slice* 为空切片，则该函数返回 1 +存在于 *slice_1* 中的 UTF-8 编码码点数。

**示例:**

```go
// Go program to illustrate how to
// count the elements of the slice
package main

import (
    "bytes"
    "fmt"
)

func main() {

    // Creating and initializing 
    // slices of bytes
    // Using shorthand declaration
    slice_1 := []byte{'A', 'N', 'M',
            'A', 'P', 'A', 'A', 'W'}

    slice_2 := []byte{'g', 'e', 'e', 'k', 's'}

    // Counting elements in the given slices
    // Using Count function
    res1 := bytes.Count(slice_1, []byte{'A'})
    res2 := bytes.Count(slice_2, []byte{'e'})
    res3 := bytes.Count([]byte("GeeksforGeeks"), []byte("ks"))
    res4 := bytes.Count([]byte("Geeks"), []byte(""))
    res5 := bytes.Count(slice_1, []byte(""))

    // Displaying results
    fmt.Println("Result 1:", res1)
    fmt.Println("Result 2:", res2)
    fmt.Println("Result 3:", res3)
    fmt.Println("Result 4:", res4)
    fmt.Println("Result 5:", res5)

}
```

**输出:**

```go
Result 1: 4
Result 2: 2
Result 3: 2
Result 4: 6
Result 5: 9

```