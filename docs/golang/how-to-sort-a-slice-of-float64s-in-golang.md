# 如何对 Golang 中的一片 float64s 进行排序？

> 原文:[https://www . geesforgeks . org/如何对 golang 中的 float64s 切片进行排序/](https://www.geeksforgeeks.org/how-to-sort-a-slice-of-float64s-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。Go 语言允许您根据切片的类型对其元素进行排序。因此， *float64* 型切片通过使用以下功能进行排序。这些函数是在排序包下定义的，因此您必须在程序中导入排序包来访问这些函数:

**1。Float64s:** 此功能仅用于对 Float64s 的一个切片进行排序，并按递增顺序对切片的元素进行排序。

**语法:**

```go
func Float64s(slc []float64)
```

这里， *slc* 代表一片*浮动 64* 。让我们借助一个例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how
// to sort a slice of float64s
package main

import (
    "fmt"
    "sort"
)

// Main function
func main() {

    // Creating and initializing slices
    // Using shorthand declaration
    scl1 := []float64{9.56, 4.56, 2.4,
                 10, 43, 0.56, 35.246}

    scl2 := []float64{38.32, -32.23, 
               -45.56, 23.45, -0.43}

    // Displaying slices
    fmt.Println("Slice(Before):")
    fmt.Println("Slice 1: ", scl1)
    fmt.Println("Slice 2: ", scl2)

    // Sorting the elements of the slice
    // Using Float64s function
    sort.Float64s(scl1)
    sort.Float64s(scl2)

    // Displaying the result
    fmt.Println("\nSlice(After):")
    fmt.Println("Slice 1: ", scl1)
    fmt.Println("Slice 2: ", scl2)
}
```

**输出:**

```go
Slice(Before):
Slice 1:  [9.56 4.56 2.4 10 43 0.56 35.246]
Slice 2:  [38.32 -32.23 -45.56 23.45 -0.43]

Slice(After):
Slice 1:  [0.56 2.4 4.56 9.56 10 35.246 43]
Slice 2:  [-45.56 -32.23 -0.43 23.45 38.32]

```

**2。float64s 排序:**此功能用于检查 float 64s 的给定切片是否为排序形式(按递增顺序)。如果切片处于排序形式，此方法返回 true 如果切片不处于排序形式，则返回 false。

**语法:**

```go
func Float64sAreSorted(scl []float64) bool
```

这里， *scl* 代表一片 float64s。让我们借助一个例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how to check whether the
// given slice of float64 is in sorted form or not
package main

import (
    "fmt"
    "sort"
)

// Main function
func main() {

    // Creating and initializing slices
    // Using shorthand declaration
    scl1 := []float64{9.56, 4.56, 2.4,
                 10, 43, 0.56, 35.246}

    scl2 := []float64{-45.56, -32.23,
                 -0.43, 23.45, 38.32}

    // Displaying slices
    fmt.Println("Slices:")
    fmt.Println("Slice 1: ", scl1)
    fmt.Println("Slice 2: ", scl2)

    // Checking the slice is in sorted form or not
    // Using Float64sAreSorted  function
    res1 := sort.Float64sAreSorted(scl1)
    res2 := sort.Float64sAreSorted(scl2)

    // Displaying the result
    fmt.Println("\nResult:")
    fmt.Println("Is Slice 1 is sorted?: ", res1)
    fmt.Println("Is Slice 2 is sorted?: ", res2)
}
```

**输出:**

```go
Slices:
Slice 1:  [9.56 4.56 2.4 10 43 0.56 35.246]
Slice 2:  [-45.56 -32.23 -0.43 23.45 38.32]

Result:
Is Slice 1 is sorted?:  false
Is Slice 2 is sorted?:  true

```