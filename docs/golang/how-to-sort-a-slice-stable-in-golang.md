# 如何在 Golang 中对稳定的切片进行排序？

> 原文:[https://www . geesforgeks . org/如何对切片进行排序-稳定在 golang/](https://www.geeksforgeeks.org/how-to-sort-a-slice-stable-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在 Go 语言中，允许使用**slicestatable()**功能对切片进行稳定排序。给定指定的 less 函数，该函数对指定的切片进行排序，同时保持相等元素的原始顺序。如果指定的接口不是一个片，这个函数就会死机。它是在排序包下定义的，所以您必须在程序中导入排序包来访问 SliceStable 函数。

**语法:**

```go
func SliceStable(a_slice interface{}, less func(p, q int) bool)
```

**示例:**

```go
// Go program to illustrate how
// to sort a slice stable
package main

import (
    "fmt"
    "sort"
)

// Main function
func main() {

    // Creating and initializing a structure
    Author := []struct {
        a_name    string
        a_article int
        a_id      int
    }{
        {"Mina", 304, 1098},
        {"Cina", 634, 102},
        {"Tina", 104, 105},
        {"Mina", 34, 109},
        {"Cina", 634, 102},
        {"Mina", 4, 100},
        {"Rohit", 56, 1098},
        {"Cina", 634, 102},
        {"Mina", 39, 1098},
        {"Sohit", 20, 110},
    }

    // Sorting Author by their names
    // Using SliceStable() function
    sort.SliceStable(Author, func(p, q int) bool { 
      return Author[p].a_name < Author[q].a_name })

    fmt.Println("Sort Author according to their names:")
    fmt.Println(Author)

    // Sorting Author by the total articles
    // Using SliceStable() function
    sort.SliceStable(Author, func(p, q int) bool {
      return Author[p].a_article < Author[q].a_article })

    fmt.Println()
    fmt.Println("Sort Author according to their"+
                    " total number of articles:")

    fmt.Println(Author)

    // Sorting Author by their ids
    // Using SliceStable() function
    sort.SliceStable(Author, func(p, q int) bool { 
          return Author[p].a_id < Author[q].a_id })

    fmt.Println()
    fmt.Println("Sort Author according to the their Ids:")
    fmt.Println(Author)
}
```

**输出:**

> 根据作者姓名对其进行排序:
> [{ Cina 634 102 } { Cina 634 102 } { Cina 634 102 } { Mina 304 1098 } { Mina 34 109 } { Mina 4 100 } { Mina 39 1098 } { Rohit 56 1098 } { Sohit 20 110 } { Tina 104 105 }]
> 
> 根据作者的文章总数对其进行排序:
> [{ Mina 4 100 } { Sohit 20 110 } { Mina 34 109 } { Mina 39 1098 } { Rohit 56 1098 } { Tina 104 105 } { Mina 304 1098 } { Cina 634 102 } { Cina 634 102 } { Cina 634 102 }]
> 
> 根据作者的 id 对其进行排序:
> [{ Mina 4 100 } { Cina 634 102 } { Cina 634 102 } { Cina 634 102 } { Tina 104 105 } { Mina 34 109 } { Sohit 20 110 } { Mina 39 1098 } { Rohit 56 1098 } { Mina 304 1098 }]