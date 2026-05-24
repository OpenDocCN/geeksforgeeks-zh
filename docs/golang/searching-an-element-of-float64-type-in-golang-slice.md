# 在戈朗切片中搜索一个 float64 类型的元素

> 原文:[https://www . geeksforgeeks . org/search-a-element-of-float 64-type-in-golang-slice/](https://www.geeksforgeeks.org/searching-an-element-of-float64-type-in-golang-slice/)

In Go 语言切片比数组更强大、灵活、方便，是一种轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在 Go 切片中，可以借助 **SearchFloat64s()** 功能，在给定的 float64s 切片中搜索 float64 类型的元素。该函数在 float64s 的排序切片中搜索给定元素，并返回该元素在给定切片中的索引。如果给定的元素在切片中不可用(它可能是 *len(s_slice)* ，那么它返回索引以将元素插入切片中。指定的切片必须按升序排序。它是在排序包下定义的，所以您必须在程序中导入排序包才能访问 *SearchFloat64s* 功能。

**语法:**

```go
func SearchFloat64s(s_slice []float64, f float64) int
```

**例 1:**

```go
// Go program to illustrate how to search an 
// element float64 type in the slice of float64s
package main

import (
    "fmt"
    "sort"
)

// Main function
func main() {

    // Creating and initializing
    // slice of Float64s
    // Using shorthand declaration
    slice_1 := []float64{45.667, 34545.5, 655.45,
                        768.8, 79.1, 10.2, 34.67}

    slice_2 := []float64{56.78, 67.89, 10.7,
                         345.6, 89.4, 45.8}

    var f1, f2, f3 float64
    f1 = 34545.5
    f2 = 67.89
    f3 = 10.7

    // Sorting the given slice of Float64s
    sort.Float64s(slice_1)
    sort.Float64s(slice_2)

    // Displaying the slices
    fmt.Println("Slice 1: ", slice_1)
    fmt.Println("Slice 2: ", slice_2)

    // Searching an element of float64
    // in the given slice
    // Using SearchFloat64s function
    res1 := sort.SearchFloat64s(slice_1, f1)
    res2 := sort.SearchFloat64s(slice_2, f2)
    res3 := sort.SearchFloat64s(slice_2, f3)

    // Displaying the results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)

}
```

**输出:**

```go
Slice 1:  [10.2 34.67 45.667 79.1 655.45 768.8 34545.5]
Slice 2:  [10.7 45.8 56.78 67.89 89.4 345.6]
Result 1:  6
Result 2:  3
Result 3:  0

```

**例 2:**

```go
// Go program to illustrate how to search an
// element of float64 type in the slice of
// float64s
package main

import (
    "fmt"
    "sort"
)

// Main function
func main() {

    // Creating and searching an element
    // in the given slice of float64s
    // Using SearchFloat64s function
    res1 := sort.SearchFloat64s([]float64{23.4,
                        56.7, 90.7}, 56.7)

    res2 := sort.SearchFloat64s([]float64{10.2,
               13.90, 25.78, 38.90}, 10.2)

    // Displaying the results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)

}
```

**输出:**

```go
Result 1:  1
Result 2:  0

```