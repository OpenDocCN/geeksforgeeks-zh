# 如何在 Golang 追加切片？

> 原文:[https://www . geesforgeks . org/如何在 golang 中追加切片/](https://www.geeksforgeeks.org/how-to-append-a-slice-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。它就像一个有索引值和长度的数组，但是切片的大小被调整，它们不像数组那样是固定大小的。
我们已经知道切片是动态的，所以可以借助 append()函数将新元素追加到切片中。该函数在切片的末尾追加新元素。

**语法:**

```go
func append(s []T, x ...T) []T
```

在这里，这个函数取 *s* 切片和 *x…T* 意味着这个函数为 *x* 参数取可变数量的参数。这种类型的函数也被称为变量函数。

***如果切片由数组支持，数组是固定长度的，那么切片怎么可能是动态长度呢？。**T3】*

答案是，当新元素附加到切片时，会创建一个新数组。现在，现有数组中的元素被复制到新数组中，并返回对该数组(新数组)的新切片引用。因此，由于这个原因，切片的容量将是旧容量的两倍(如示例 1 所示)。但是如果现有的切片有足够的容量来容纳新的元素，那么就不会创建新的数组，元素会存储在现有的底层数组中(如示例 2 所示)。

**例 1:**

```go
// Go program to illustrate the
// concept of appending slices.
package main

import (
    "fmt"
)

func main() {

    // Creating and initializing slice
    // Using shorthand declaration
    s1 := []int{234, 567, 7890, 1234, 234}
    s2 := []string{"Geeks", "For", "Geeks"}

    // Displaying slices with
    // their length and capacity
    fmt.Println("Slice_1: ", s1)
    fmt.Println("Length of Slice_1: ", len(s1))
    fmt.Println("Capacity of Slice_1: ", cap(s1))
    fmt.Println()
    fmt.Println("Slice_2: ", s2)
    fmt.Println("Length of Slice_2: ", len(s2))
    fmt.Println("Capacity of Slice_2: ", cap(s2))

    // Appending slices
    // Using append() function
    res1 := append(s1, 1000)
    res2 := append(s2, "GFG")

    // Displaying results
    fmt.Println()
    fmt.Println("New slice_1: ", res1)
    fmt.Println("New length of slice_1: ", len(res1))
    fmt.Println("New capacity of slice_1: ", cap(res1))
    fmt.Println()
    fmt.Println("New slice_2: ", res2)
    fmt.Println("New length of slice_2: ", len(res2))
    fmt.Println("New capacity of slice_2: ", cap(res2))
}
```

**输出:**

```go
Slice_1:  [234 567 7890 1234 234]
Length of Slice_1:  5
Capacity of Slice_1:  5

Slice_2:  [Geeks For Geeks]
Length of Slice_2:  3
Capacity of Slice_2:  3

New slice_1:  [234 567 7890 1234 234 1000]
New length of slice_1:  6
New capacity of slice_1:  12

New slice_2:  [Geeks For Geeks GFG]
New length of slice_2:  4
New capacity of slice_2:  6

```

**例 2:**

```go
// Go program to illustrate the
// concept of appending slices.
package main

import "fmt"

func main() {

    // Creating and initializing slice
    // Using make() function
    // Here 4 and 6 is the length
    // and capacity of the slice
    s1 := make([]int, 4, 6)

    // Copying the elements in the slice
    // Using copy() function
    copy(s1, []int{123, 456, 789, 977})

    // Displaying slice
    fmt.Println("Slice : ", s1)
    fmt.Println("Length: ", len(s1))
    fmt.Println("Capacity: ", cap(s1))

    // Appending slice
    // Using append() function
    s2 := append(s1, 3454, 678)

    // Displaying slice
    fmt.Println()
    fmt.Println("Slice : ", s2)
    fmt.Println("Length: ", len(s2))
    fmt.Println("Capacity: ", cap(s2))

}
```

**输出:**

```go
Slice :  [123 456 789 977]
Length:  4
Capacity:  6

Slice :  [123 456 789 977 3454 678]
Length:  6
Capacity:  6

```

**追加到零切片:**我们知道，零值切片类型是零，这种类型切片的容量和长度是 0。但是在 append 函数的帮助下，可以将值追加到 nil 切片中。

**示例:**

```go
// Go program to illustrate the
// concept of appending to nil slice.
package main

import "fmt"

func main() {

    // Creating nil slice
    var s1 []int

    // Displaying slice
    fmt.Println("Slice : ", s1)
    fmt.Println("Length: ", len(s1))
    fmt.Println("Capacity: ", cap(s1))

    // Appending to nil slice
    // Using append() function
    s2 := append(s1, 89, 45, 67, 23)

    // Displaying slice
    fmt.Println()
    fmt.Println("Slice : ", s2)
    fmt.Println("Length: ", len(s2))
    fmt.Println("Capacity: ", cap(s2))

}
```

**输出:**

```go
Slice :  []
Length:  0
Capacity:  0

Slice :  [89 45 67 23]
Length:  4
Capacity:  4

```

**使用…运算符追加到另一个切片:**您可以在 **…** 运算符的帮助下将一个切片追加到另一个切片。

**示例:**

```go
// Go program to illustrate the concept 
// of appending to another slice.
package main

import "fmt"

func main() {

    // Creating and initializing slice
    // Using shorthand declaration
    s1 := []int{234, 567, 7890, 1234, 234}
    s2 := []int{10, 100, 1000, 10000}

    // Displaying slices with their
    // length and capacity
    fmt.Println("Slice_1: ", s1)
    fmt.Println("Length of Slice_1: ", len(s1))
    fmt.Println("Capacity of Slice_1: ", cap(s1))

    fmt.Println()

    fmt.Println("Slice_2: ", s2)
    fmt.Println("Length of Slice_2: ", len(s2))
    fmt.Println("Capacity of Slice_2: ", cap(s2))

    // Appending to another slice
    // Using append() function
    res1 := append(s1, s2...)

    // Displaying result
    fmt.Println()
    fmt.Println("New slice_1: ", res1)
    fmt.Println("New length of slice_1: ", len(res1))
    fmt.Println("New capacity of slice_1: ", cap(res1))

}
```

**输出:**

```go
Slice_1:  [234 567 7890 1234 234]
Length of Slice_1:  5
Capacity of Slice_1:  5

Slice_2:  [10 100 1000 10000]
Length of Slice_2:  4
Capacity of Slice_2:  4

New slice_1:  [234 567 7890 1234 234 10 100 1000 10000]
New length of slice_1:  9
New capacity of slice_1:  12

```