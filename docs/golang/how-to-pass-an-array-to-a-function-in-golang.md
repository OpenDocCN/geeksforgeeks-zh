# 如何在 Golang 中将数组传递给函数？

> 原文:[https://www . geesforgeks . org/如何将数组传递给函数 in-golang/](https://www.geeksforgeeks.org/how-to-pass-an-array-to-a-function-in-golang/)

[Golang 或 Go 编程语言中的数组](https://www.geeksforgeeks.org/arrays-in-go/)与其他编程语言非常相似。在程序中，有时我们需要存储一组相同类型的数据，比如学生成绩列表。这种类型的集合存储在使用数组的程序中。数组是固定长度的序列，用于在内存中存储同类元素。
在 Go 语言中，允许在函数中传递数组作为参数。要在函数中传递数组作为参数，必须首先使用以下语法创建一个形式参数:

**语法:**

```go
// For sized array
func function_name(variable_name [size]type){
// Code
}
```

使用此语法，您可以将一维或多维数组传递给函数。让我们借助一个例子来讨论这个概念:

**示例:**

## 去

```go
// Go program to illustrate how to pass an
// array as an argument in the function
package main

import "fmt"

// This function accept
// an array as an argument
func myfun(a [6]int, size int) int {
    var k, val, r int

    for k = 0; k < size; k++ {
        val += a[k]
    }

    r = val / size
    return r
}

// Main function
func main() {

    // Creating and initializing an array
    var arr = [6]int{67, 59, 29, 35, 4, 34}
    var res int

    // Passing an array as an argument
    res = myfun(arr, 6)
    fmt.Printf("Final result is: %d ", res)
}
```

**输出:**

```go
Final result is: 38 
```

**说明:**在上面的例子中，我们有一个名为 *myfun()* 的函数，它接受一个数组作为参数。在主函数中，我们将 int 类型的*arr【6】*传递给具有数组大小的函数，该函数返回数组的平均值。