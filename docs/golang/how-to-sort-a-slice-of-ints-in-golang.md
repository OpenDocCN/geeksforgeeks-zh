# 如何对 Golang 中的一片 ints 进行排序？

> 原文:[https://www . geeksforgeeks . org/如何对 golang 中的一片 ints 进行排序/](https://www.geeksforgeeks.org/how-to-sort-a-slice-of-ints-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
Go 语言允许您根据切片的类型对其元素进行排序。因此，使用以下函数对 int 类型的切片进行排序。这些函数是在排序包下定义的，因此您必须在程序中导入排序包来访问这些函数:

**1。Ints:** 这个函数只用于对 Ints 的一个切片进行排序，它按照递增的顺序对切片的元素进行排序。

**语法:**

```go
func Ints(slc []int)
```

这里， *slc* 代表一片 ints。让我们借助一个例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how 
// to sort the slice of ints
package main

import (
    "fmt"
    "sort"
)

// Main function
func main() {

    // Creating and initializing slices
    // Using shorthand declaration
    scl1 := []int{400, 600, 100, 300, 500, 200, 900}
    scl2 := []int{-23, 567, -34, 67, 0, 12, -5}

    // Displaying slices
    fmt.Println("Slices(Before):")
    fmt.Println("Slice 1: ", scl1)
    fmt.Println("Slice 2: ", scl2)

    // Sorting the slice of ints
    // Using Ints function
    sort.Ints (scl1)
    sort.Ints (scl2)

    // Displaying the result
    fmt.Println("\nSlices(After):")
    fmt.Println("Slice 1 : ", scl1)
    fmt.Println("Slice 2 : ",scl2)
}
```

**输出:**

```go
Slices(Before):
Slice 1:  [400 600 100 300 500 200 900]
Slice 2:  [-23 567 -34 67 0 12 -5]

Slices(After):
Slice 1 :  [100 200 300 400 500 600 900]
Slice 2 :  [-34 -23 -5 0 12 67 567]

```

**2。IntsAreSorted:** 此函数用于检查给定的 ints 切片是否处于排序形式(按递增顺序)。如果切片处于排序形式，此方法返回 true 如果切片不处于排序形式，则返回 false。

**语法:**

```go
func IntsAreSorted(scl []int) bool
```

这里， *scl* 代表 *ints* 的一部分。让我们借助一个例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how to check
// whether the given slice of ints is in
// sorted form or not
package main

import (
    "fmt"
    "sort"
)

// Main function
func main() {

    // Creating and initializing slices
    // Using shorthand declaration
    scl1 := []int{100, 200, 300, 400, 500, 600, 700}
    scl2 := []int{-23, 567, -34, 67, 0, 12, -5}

    // Displaying slices
    fmt.Println("Slices:")
    fmt.Println("Slice 1: ", scl1)
    fmt.Println("Slice 2: ", scl2)

    // Checking the slice is in sorted form or not
    // Using IntsAreSorted function
    res1 := sort.IntsAreSorted(scl1)
    res2 := sort.IntsAreSorted(scl2)

    // Displaying the result
    fmt.Println("\nResult:")
    fmt.Println("Is Slice 1 is sorted?: ", res1)
    fmt.Println("Is Slice 2 is sorted?: ", res2)
}
```

**输出:**

```go
Slices:
Slice 1:  [100 200 300 400 500 600 700]
Slice 2:  [-23 567 -34 67 0 12 -5]

Result:
Is Slice 1 is sorted?:  true
Is Slice 2 is sorted?:  false

```