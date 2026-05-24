# 格朗切片

> 原文:[https://www.geeksforgeeks.org/slice-of-slices-in-golang/](https://www.geeksforgeeks.org/slice-of-slices-in-golang/)

在 Go 语言中，[](https://www.geeksforgeeks.org/slices-in-golang/)**切片是一种关键的数据类型，与数组相比，它既强大又灵活。切片是对数组的抽象，克服了数组的限制，如动态获取大小或创建自己的子数组，因此比传统数组更方便使用。它就像一个数组，有一个索引值和长度，但是切片的大小被调整，它们不像数组一样是固定大小的。切片只存储相同类型的元素，不同类型的元素不能存储在同一切片中。**

**切片是通过指定两个索引(下限和上限)形成的，由冒号分隔，如下所示:**

> **arr[下限:上限]** 
> 
> **这包括下限，但不包括上限，其中*下限*的最小值可以是 0，*上限*的最大值可以是 *arr* 数组的长度。**

**为了制作切片的**切片，我们可以将它们组合成类似于 2D 阵列的多维数据结构。这是通过使用名为 ***make()*** 的函数来完成的，该函数创建一个非零长度的空切片。这在以下示例中显示:****

## **去**

```go
package main

import (
    "fmt"
)

// main function
func main() {

    // declaring a slice of slices of
    // type integer with a length of 3
    slice_of_slices := make([][]int , 3)

    for i := 0; i < 3; i++ {
        // looping through the slice to declare
        // slice of slice of length 3
        slice_of_slices[i] = make([]int, 3)

        // assigning values to each
        // slice of a slice
        for j := 0; j < 3; j++{
            slice_of_slices[i][j] = i * j
        }
    }

    // printing the slice of slices matrix
    for i := 0; i < 3; i++ {
        fmt.Println(slice_of_slices[i])
    }

    fmt.Println("Slice of slices: ", slice_of_slices)
}
```

****输出:****

```go
[0 0 0]
[0 1 2]
[0 2 4]
Slice of slices:  [[0 0 0] [0 1 2] [0 2 4]]
```

**由于切片的动态特性，可以有一个可变的切片。如下例所示:**

## **去**

```go
package main

import (
    "fmt"
)

// main function
func main() {

    // declaring a slice of slices of
    // type integer with a length of 3
    slice_of_slices := make([][]int , 3)

    for i := 0; i < 3; i++ {

        new_length := i * 2 + 1
        // looping through the slice to declare
        // slice of slice of a variable length
        slice_of_slices[i] = make([]int, new_length)

        // assigning values to each
        // slice of a slice
        for j := 0; j < new_length; j++{
            slice_of_slices[i][j] = i * j + 1
        }
    }

    // printing the slice of slices matrix
    for i := 0; i < 3; i++ {
        fmt.Println(slice_of_slices[i])
    }

    fmt.Println("Slice of slices: ", slice_of_slices)
}
```

****输出:****

```go
[1]
[1 2 3]
[1 3 5 7 9]
Slice of slices:  [[1] [1 2 3] [1 3 5 7 9]]
```