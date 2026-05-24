# 如何在 Golang 中对切片进行排序？

> 原文:[https://www . geesforgeks . org/如何对 golang 中的切片进行排序/](https://www.geeksforgeeks.org/how-to-sort-a-slice-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在 Go 语言中，可以借助 **Slice()** 功能对切片进行排序。给定提供的较少函数，此函数对指定的切片进行排序。这个函数的结果不稳定。所以对于稳定排序，可以使用 SliceStable。如果指定的接口不是片类型，这个函数就会死机。它是在排序包下定义的，所以您必须在程序中导入排序包来访问切片函数。

**语法:**

```go
func Slice(a_slice interface{}, less func(p, q int) bool)
```

**示例:**

```go
// Go program to illustrate
// how to sort a slice
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

    fmt.Println("Sort Author according to their names:")
    fmt.Println(Author)

    // Sorting Author by their
    // total number of articles
    // Using Slice() function
    sort.Slice(Author, func(p, q int) bool { 
       return Author[p].a_article < Author[q].a_article })

    fmt.Println()
    fmt.Println("Sort Author according to their"+
                    " total number of articles:")

    fmt.Println(Author)

    // Sorting Author by their ids
    // Using Slice() function
    sort.Slice(Author, func(p, q int) bool { 
     return Author[p].a_id < Author[q].a_id })

    fmt.Println()
    fmt.Println("Sort Author according to the their Ids:")
    fmt.Println(Author)
}
```

**输出:**

> 根据作者姓名对其进行排序:
> [{ Cina 634 102 } { Mina 304 1098 } { Mohit 300 104 } { Rina 10 108 } { Riya 4 101 } { Rohit 56 107 } { Sina 234 103 } { Sohit 20 110 } { Tina 104 105 } { Vina 237 106 }]
> 
> 根据作者的文章总数对其进行排序:
> [{ Riya 4 101 } { Rina 10 108 } { Sohit 20 110 } { Rohit 56 107 } { Tina 104 105 } { Sina 234 103 } { Vina 237 106 } { Mohit 300 104 } { Mina 304 1098 } { Cina 634 102 }]
> 
> 根据作者的 id 对其进行排序:
> [{ Riya 4 101 } { Cina 634 102 } { Sina 234 103 } { Mohit 300 104 } { Tina 104 105 } { Vina 237 106 } { Rohit 56 107 } { Rina 10 108 } { Sohit 20 110 } { Mina 304 1098 }]