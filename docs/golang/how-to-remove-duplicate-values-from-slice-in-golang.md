# 如何去除 Golang 中切片的重复值？

> 原文:[https://www . geesforgeks . org/如何从 golang 切片中删除重复值/](https://www.geeksforgeeks.org/how-to-remove-duplicate-values-from-slice-in-golang/)

[数组](https://www.geeksforgeeks.org/arrays-in-go/)是一种数据结构。同样，在 Golang 中，我们有比数组更灵活、更强大、更轻量级和更方便的切片。由于[切片](https://www.geeksforgeeks.org/slices-in-golang/)比阵列更灵活，因此其灵活性取决于其大小。就像数组一样，它有索引值和长度，但是它的大小不是固定的。当我们声明一个切片时，我们不指定它的大小。
**语法:**

```go
[]mySlice;
 OR
[]mySlice{};
OR
[]mySlice{input1, input2, .........input n}
```

此外，切片和数组是相互连接的，在切片中，有对底层数组的引用。在切片中，我们可以存储重复的元素。
**示例:**在这里，我们将看到如何从切片中移除重复的元素。我们已经定义了一个传递切片值的函数，并使用映射函数来检查和删除重复的值。

## C

```go
// Golang program to remove duplicate
// values from Slice
package main

import (
    "fmt"
)

func removeDuplicateValues(intSlice []int) []int {
    keys := make(map[int]bool)
    list := []int{}

    // If the key(values of the slice) is not equal
    // to the already present value in new slice (list)
    // then we append it. else we jump on another element.
    for _, entry := range intSlice {
        if _, value := keys[entry]; !value {
            keys[entry] = true
            list = append(list, entry)
        }
    }
    return list
}

func main() {

    // Assigning values to the slice
    intSliceValues := []int{1,2,3,4,5,2,3,5,7,9,6,7}

    // Printing original value of slice
    fmt.Println(intSliceValues)

    // Calling function where we
    // are removing the duplicates
    removeDuplicateValuesSlice := removeDuplicateValues(intSliceValues)

    // Printing the filtered slice
    // without duplicates
    fmt.Println(removeDuplicateValuesSlice)
}
```

**输出:**

```go
[1 2 3 4 5 2 3 5 7 9 6 7]
[1 2 3 4 5 7 9 6]
```

**说明:**

*   从主函数中，我们已经声明了一个切片。我们还打印了切片的原始值。
*   我们定义了一个函数，传递切片的原始值并检查重复值。
*   **重复检查逻辑:**为此，我们定义了另一个切片，并通过检查该值是否已经存在于新切片中来分配第一个值。它返回没有重复的切片。
*   我们从打印函数返回切片的主函数中调用*remove replicateevalues*函数。