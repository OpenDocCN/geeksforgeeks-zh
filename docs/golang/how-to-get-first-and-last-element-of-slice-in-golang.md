# 如何获取 Golang 中切片的首末元素？

> 原文:[https://www . geesforgeks . org/如何获取 golang 中切片的第一个和最后一个元素/](https://www.geeksforgeeks.org/how-to-get-first-and-last-element-of-slice-in-golang/)

Go 语言切片比数组更强大、灵活、方便，是一种轻量级的数据结构。[切片](https://www.geeksforgeeks.org/slices-in-golang/)是存储相似类型元素的变长序列，不允许在同一个切片中存储不同类型的元素。它就像一个有索引值和长度的数组，但是切片的大小被调整，它们不像数组那样是固定大小的。在内部，切片和数组是相互连接的，切片是对底层数组的引用。允许在切片中存储重复的元素。切片中的第一个索引位置总是 0，最后一个总是(切片长度–1)。

**访问第一个元素:**使用切片的*第零个*索引很容易访问第一个元素。

**访问最后一个元素:**最后一个元素是位于索引位置的元素，即切片的*长度*减去 *1* 。

**示例:**

```go
Input : 
sliceOfInt[]=[2, 3, 4, 5, 6]

Output :
First element : 2
Last element : 6

Input : 
sliceOfFloat[]=[4.5, 3.4, 6.6, 5.2, 2.1]

Output :
First element : 4.5
Last element : 2.1

```

**例 1:**

```go
// Golang program to access the first
// and last element of the slice

package main

import "fmt"

func main() {

    // Declaring & Defining
    // the Slice
    sliceOfInt := []int{2, 3, 4, 5, 6}

    // Printing the Slice
    fmt.Printf("Slice: %v\n", sliceOfInt)

    // Accessing zeroth index
    // i.e. first element
    first := sliceOfInt[0]

    // Printing first element
    fmt.Printf("First element: %d\n", first)

    // Accessing length(slice)-1
    // index i.e. last
    // element
    last := sliceOfInt[len(sliceOfInt)-1]

    // Printing last element
    fmt.Printf("Last element: %v\n", last)

}
```

**输出:**

```go
Slice: [2 3 4 5 6]
First element: 2
Last element: 6

```

**例 2:**

```go
// Golang program to access the first
// and last element of the slice
package main

import "fmt"

func main() {

    sliceOfFloat := []float32{2.5, 3.2, 4.1, 5.7, 6.9}
    fmt.Printf("Slice: %v\n", sliceOfFloat)

    first := sliceOfFloat[0]
    fmt.Printf("First element: %v\n", first)

    last := sliceOfFloat[len(sliceOfFloat)-1]
    fmt.Printf("Last element: %v\n", last)

}
```

**输出:**

```go
Slice: [2.5 3.2 4.1 5.7 6.9]
First element: 2.5
Last element: 6.9

```