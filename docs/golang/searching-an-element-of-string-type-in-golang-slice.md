# 在 Golang 切片中搜索字符串类型的元素

> 原文:[https://www . geesforgeks . org/search-一个字符串类型的元素在 golang-slice/](https://www.geeksforgeeks.org/searching-an-element-of-string-type-in-golang-slice/)

In Go 语言切片比数组更强大、灵活、方便，是一种轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在 Go 切片中，可以借助 **SearchStrings()** 功能在给定的字符串切片中搜索字符串类型的元素。该函数在排序的字符串片段中搜索给定的元素，并返回该元素在给定片段中的索引。如果给定的元素在切片中不可用(它可能是 *len(s_slice)* ，那么它返回索引以将元素插入切片中。指定的切片必须按升序排序。它是在排序包下定义的，所以您必须在程序中导入排序包来访问搜索字符串函数。

**语法:**

```go
func SearchStrings(s_slice []string, s string64) int
```

**例 1:**

```go
// Go program to illustrate how to search an
// element of string type in the slice of strings
package main

import (
    "fmt"
    "sort"
)

// Main function
func main() {

    // Creating and initializing 
    // slice of strings
    // Using shorthand declaration
    slice_1 := []string{"C", "Go", "Java", "C#", "Ruby"}
    slice_2 := []string{"GEEKs", "123geeks", "gfg", "GeeksforGeeks"}

    var f1, f2, f3 string
    f1 = "GEEKs"
    f2 = "C"
    f3 = "gfg"

    // Sorting the given 
    // slice of strings
    sort.Strings(slice_1)
    sort.Strings(slice_2)

    // Displaying the slices
    fmt.Println("Slice 1: ", slice_1)
    fmt.Println("Slice 2: ", slice_2)

    // Searching a int type element 
    // in the given slice
    // Using SearchStrings function
    res1 := sort.SearchStrings(slice_1, f1)
    res2 := sort.SearchStrings(slice_2, f2)
    res3 := sort.SearchStrings(slice_2, f3)

    // Displaying the results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)

}
```

**输出:**

```go
Slice 1:  [C C# Go Java Ruby]
Slice 2:  [123geeks GEEKs GeeksforGeeks gfg]
Result 1:  2
Result 2:  1
Result 3:  3

```

**例 2:**

```go
// Go program to illustrate how to search an element
// of string type in the slice of strings
package main

import (
    "fmt"
    "sort"
)

// Main function
func main() {

    // Creating and searching an element
    // in the given slice of strings
    // Using SearchStrings function
    res1 := sort.SearchStrings([]string{"apple", "banana",
                                "kiwi", "orange"}, "kiwi")

    res2 := sort.SearchStrings([]string{"Cat", "Cow",
                             "Dog", "Parrot"}, "Cat")

    // Displaying the results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)

}
```

**输出:**

```go
Result 1:  2
Result 2:  0

```