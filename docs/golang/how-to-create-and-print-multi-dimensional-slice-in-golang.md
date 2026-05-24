# 如何在 Golang 创建和打印多维切片？

> 原文:[https://www . geesforgeks . org/如何创建和打印多维切片在 golang/](https://www.geeksforgeeks.org/how-to-create-and-print-multi-dimensional-slice-in-golang/)

[切片](https://www.geeksforgeeks.org/slices-in-golang/)是存储相似类型元素的变长序列，不允许在同一个切片中存储不同类型的元素。它就像一个有索引值和长度的数组，但是切片的大小被调整，它们不像数组那样是固定大小的。在内部，切片和数组是相互连接的，切片是对底层数组的引用。允许在切片中存储重复的元素。切片中的第一个索引位置始终为 0，最后一个索引位置为(切片长度–1)。

**多维切片**就像多维数组一样，只是切片不包含大小。

**示例:**

```go
// Golang program to illustrate
// the multi-dimensional slice
package main

import "fmt"

func main() {

    // Creating multi-dimensional slice
    s1 := [][]int{
        {1, 2},
        {3, 4},
        {5, 6},
        {7, 8},
    }

    // Accessing multi-dimensional slice
    fmt.Println("Slice 1 : ", s1)

    // Creating multi-dimensional slice
    s2 := [][]string{
        []string{"str1", "str2"},
        []string{"str3", "str4"},
        []string{"str5", "str6"},
    }

    // Accessing multi-dimensional slice
    fmt.Println("Slice 2 : ", s2)

    // Printing every slice inside s2
    fmt.Println("MultiDimensional Slice s2:")
    for i := 0; i < len(s2); i++ {
        fmt.Println(s2[i])
    }

    // Printing elements in slice as matrix
    fmt.Println("Slice s2 Like Matrix:")

    // number of rows in s2
    n := len(s2)

    // number of columns in s2
    m := len(s2[0])
    for i := 0; i < n; i++ {
        for j := 0; j < m; j++ {
            fmt.Print(s2[i][j] + " ")
        }
        fmt.Print("\n")
    }
}
```

**输出:**

```go
Slice 1 :  [[1 2] [3 4] [5 6] [7 8]]
Slice 2 :  [[str1 str2] [str3 str4] [str5 str6]]
MultiDimensional Slice s2:
[str1 str2]
[str3 str4]
[str5 str6]
Slice s2 Like Matrix:
str1 str2 
str3 str4 
str5 str6 

```