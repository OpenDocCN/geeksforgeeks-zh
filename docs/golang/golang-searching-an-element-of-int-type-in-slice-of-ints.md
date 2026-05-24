# Golang |在 int 的切片中搜索 int 类型的元素

> 原文:[https://www . geeksforgeeks . org/golang-search-in-in-in-in-slice-of-ints 中的一个元素/](https://www.geeksforgeeks.org/golang-searching-an-element-of-int-type-in-slice-of-ints/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在 Go 切片中，可以借助 **SearchInts()** 功能在给定的 int 切片中搜索 int 类型的元素。该函数在一个已排序的 int 切片中搜索给定的元素，并返回该元素在给定切片中的索引。如果给定的元素在切片中不可用(它可能是 len(s_slice))，那么它返回索引以将元素插入切片中。指定的切片必须按升序排序。它是在排序包下定义的，所以您必须在程序中导入排序包来访问搜索功能。

**语法:**

```go
func SearchInts(s_slice []int, i int) int
```

**例 1:**

```go
// Go program to illustrate how to search
// an int type element in the slice of ints
package main

import (
    "fmt"
    "sort"
)

// Main function
func main() {

    // Creating and searching an element 
    // in the given slice of ints
    // Using SearchInts function
    res1 := sort.SearchInts([]int{1, 2, 3,
                        4, 5, 6, 7, 8}, 5)

    res2 := sort.SearchInts([]int{200, 300, 
                 400, 500, 600, 700}, 400)

    // Displaying the results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)

}
```

**输出:**

```go
Result 1:  4
Result 2:  2

```

**例 2:**

```go
// Go program to illustrate how to search an 
// element of int type in the slice of ints
package main

import (
    "fmt"
    "sort"
)

// Main function
func main() {

    // Creating and initializing
    // slice of ints using the 
    // shorthand declaration
    slice_1 := []int{34, 67, 78, 10, 43, 67, 8}
    slice_2 := []int{100, 500, 300, 600, 900, 1000}

    var f1, f2, f3 int
    f1 = 67
    f2 = 300
    f3 = 100

    // Sorting the given slice of ints
    sort.Ints(slice_1)
    sort.Ints(slice_2)

    // Displaying the slices
    fmt.Println("Slice 1: ", slice_1)
    fmt.Println("Slice 2: ", slice_2)

    // Searching a int type element 
    // in the given slice using 
    // the SearchInts function
    res1 := sort.SearchInts(slice_1, f1)
    res2 := sort.SearchInts(slice_2, f2)
    res3 := sort.SearchInts(slice_2, f3)

    // Displaying the results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)

}
```

**输出:**

```go
Slice 1:  [8 10 34 43 67 67 78]
Slice 2:  [100 300 500 600 900 1000]
Result 1:  4
Result 2:  1
Result 3:  0

```