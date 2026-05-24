# 如何在 Golang 中将一个切片复制到另一个切片？

> 原文:[https://www . geeksforgeeks . org/如何将一个切片复制到另一个切片中/golang/](https://www.geeksforgeeks.org/how-to-copy-one-slice-into-another-slice-in-golang/)

A [切片](https://www.geeksforgeeks.org/slices-in-golang/)是一个存储相似类型元素的变长序列，不允许在同一个切片中存储不同类型的元素。在切片中，您可以使用 Go 语言提供的**复制()功能**将一个切片复制到另一个切片中。或者换句话说，copy()函数允许您将一个切片的元素复制到另一个切片中。

**语法:**

```go
func copy(dst, src []Type) int
```

这里， *dst* 代表目的切片， *src* 代表源切片。它将返回复制元素的数量，即 *len(dst)* 或 *len(src)* 的**最小值。让我们借助给定的例子讨论一下:**

**例 1:**

```go
// Go program to illustrate how to copy 
// a slice into another slice using the
// copy function
package main

import "fmt"

// Main Method
func main() {

    // Creating slices
    slc1 := []int{58, 69, 40, 45, 11, 56, 67, 21, 65}
    var slc2 []int
    slc3 := make([]int, 5)
    slc4 := []int{78, 50, 67, 77}

    // Before copying
    fmt.Println("Slice_1:", slc1)
    fmt.Println("Slice_2:", slc2)
    fmt.Println("Slice_3:", slc3)
    fmt.Println("Slice_4:", slc4)

    // Copying the slices
    copy_1 := copy(slc2, slc1)
    fmt.Println("\nSlice:", slc2)
    fmt.Println("Total number of elements copied:", copy_1)

    copy_2 := copy(slc3, slc1)
    fmt.Println("\nSlice:", slc3)
    fmt.Println("Total number of elements copied:", copy_2)

    copy_3 := copy(slc4, slc1)
    fmt.Println("\nSlice:", slc4)
    fmt.Println("Total number of elements copied:", copy_3)

    // Don't confuse here, because in above 
    // line of code the slc4 has been copied 
    // and hence modified permanently i.e. 
    // slc 4 contains [58 69 40 45]
    copy_4:= copy(slc1, slc4)
    fmt.Println("\nSlice:", slc1)
    fmt.Println("Total number of elements copied:", copy_4)

}
```

**输出:**

```go
Slice_1: [58 69 40 45 11 56 67 21 65]
Slice_2: []
Slice_3: [0 0 0 0 0]
Slice_4: [78 50 67 77]

Slice: []
Total number of elements copied: 0

Slice: [58 69 40 45 11]
Total number of elements copied: 5

Slice: [58 69 40 45]
Total number of elements copied: 4

Slice: [58 69 40 45 11 56 67 21 65]
Total number of elements copied: 4

```

**说明:**在上面的例子中，我们有四个整数类型的切片，我们对它们执行复制操作:

*   *copy_1:= copy(slc2，slc1):* 这里， *slc2* 为目的切片， *slc1* 为源切片。这里 *slc2* 是零切片当我们试图复制 *slc2* 切片中的 *slc1* 切片时，那么复制方法将返回源和目标切片的最小长度，对于空切片 slc2，该长度为零。
*   *copy_2:= copy(slc3，slc1):* 这里， *slc3* 为目的切片， *slc1* 为源切片。这里 *slc3* 切片是空切片，所以当我们尝试使用 copy()函数将 *slc1* 切片复制到 *slc3* 时，它只从索引 0 开始从 *slc1* 切片复制 5 个元素，因为这个切片的长度是 5，所以它不能存储大于 5 的元素。
*   *copy_3:= copy(slc4，slc1):* 这里， *slc4* 为目的切片， *slc1* 为源切片。当我们尝试使用 copy()函数将 *slc1* 切片复制到 *slc4* 切片时，它只复制其中的 4 个元素，从索引 0 开始。因为 *slc4* 切片的长度是 4，所以存储元素不能超过 4 个。
*   *copy_4:= copy(slc1，slc4):* 在这里，你可能会在它输出后感到困惑。参见， *slc4* 已在上述代码行中更新。所以现在考虑一下 *slc4* 的更新值。所以现在 *slc4* 有 4 个元素， *slc1* 有 9 个元素。因此，将被复制的元素总数是 4。

**例 2:**

```go
// Go program to illustrate how to copy 
// a slice into another slice using the
// copy function
package main

import "fmt"

func main() {

    // source slice
    slice_1 := []string{"Geeks", "for", "Geeks", "GFG"}

    // creating destination slice
    // using make function
    slice_2 := make([]string, 3)

    // Before Copying
    fmt.Println("Slice_1: ", slice_1)
    fmt.Println("Slice_2: ", slice_2)

    // Copying slice_1 into slice_2
    // using copy function
    Copy_1 := copy(slice_2, slice_1)
    fmt.Println("\nSlice_1: ", slice_1)
    fmt.Println("Slice_2: ", slice_2)
    fmt.Println("Number of elements copied: ", Copy_1)

    // Copying the slice
    // using copy function
    // see the code clearly
    Copy_2 := copy(slice_1, []string{"123geeks", "gfg"})
    fmt.Println("\nSlice_1 : ", slice_1)
    fmt.Println("Number of elements copied:", Copy_2)

}
```

**输出:**

```go
Slice_1:  [Geeks for Geeks GFG]
Slice_2:  [  ]

Slice_1:  [Geeks for Geeks GFG]
Slice_2:  [Geeks for Geeks]
Number of elements copied:  3

Slice_1:  [123geeks gfg Geeks GFG]
Number of elements copied: 2

```