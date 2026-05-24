# 检查给定切片是否在 Golang 中排序

> 原文:[https://www . geeksforgeeks . org/check-如果给定切片是在 golang 中排序的/](https://www.geeksforgeeks.org/check-if-the-given-slice-is-sorted-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在 Go 语言中，可以借助**sliceissued()**功能检查给定切片是否排序。如果给定切片已排序，此函数返回 true。如果给定的切片没有排序，则返回 false。如果指定的接口不是片类型，这个函数会死机。它是在排序包下定义的，所以您必须在程序中导入排序包来访问 SliceIsSorted 函数。

**语法:**

```go
func SliceIsSorted(a_slice interface{}, less func(p, q int) bool) bool
```

**示例:**

```go
// Go program to illustrate how to check
// the given slice is sorted or not
package main

import (
    "fmt"
    "sort"
)

// Main function
func main() {

    // Creating and initializing
    // a structure
    Author := []struct {
        a_name    string
        a_article int
        a_id      int
    }{
        {"Mina", 304, 1098},
        {"Cina", 634, 102},
        {"Tina", 104, 105},
        {"Rina", 10, 108},
        {"Sina", 234, 103},
        {"Vina", 237, 106},
        {"Rohit", 56, 107},
        {"Mohit", 300, 104},
        {"Riya", 4, 101},
        {"Sohit", 20, 110},
    }

    // Sorting Author by their name
    // Using Slice() function
    sort.Slice(Author, func(p, q int) bool { 
     return Author[p].a_name < Author[q].a_name })

    // Checking the slice is sorted
    // according to their names
    // Using SliceIsSorted function
    res1 := sort.SliceIsSorted(Author, func(p, q int) bool { 
               return Author[p].a_name < Author[q].a_name })

    if res1 == true {

        fmt.Println("Slice is sorted by their names")

    } else {

        fmt.Println("Slice is not sorted by their names")
    }

    // Checking the slice is sorted 
    // according to their total articles
    // Using SliceIsSorted function
    res2 := sort.SliceIsSorted(Author, func(p, q int) bool { 
         return Author[p].a_article < Author[q].a_article })

    if res2 == true {

        fmt.Println("Slice is sorted by "+
         "their total number of articles")

    } else {

        fmt.Println("Slice is not sorted by"+
           " their total number of articles")
    }

    // Sorting Author by their ids
    // Using Slice() function
    sort.Slice(Author, func(p, q int) bool { 
      return Author[p].a_id < Author[q].a_id })

    // Checking the slice is sorted
    // according to their ids
    // Using SliceIsSorted function
    res3 := sort.SliceIsSorted(Author, func(p, q int) bool { 
                   return Author[p].a_id < Author[q].a_id })

    if res3 == true {

        fmt.Println("Slice is sorted by their ids")

    } else {

        fmt.Println("Slice is not sorted by their ids")
    }
}
```

**输出:**

```go
Slice is sorted by their names
Slice is not sorted by their total number of articles
Slice is sorted by their ids

```