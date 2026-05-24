# 检查 Golang 中 Unicode 大小写折叠下的字节片是否相等

> 原文:[https://www . geeksforgeeks . org/checking-slice-of-bytes-for-equality-under-unicode-case-folding-in-golang/](https://www.geeksforgeeks.org/checking-slice-of-bytes-for-equality-under-unicode-case-folding-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在字节的 Go 切片中，借助 ***EqualFold** ()* 功能，即使这些切片的元素写在不同的情况下(小写和大写)，您也可以毫无错误地相互比较两个切片。或者换句话说，此函数用于检查指定的切片是否被解释为 UTF-8 字符串，并且在 Unicode 大小写折叠下是否相等。如果给定切片在 Unicode 大小写折叠下相等，则此函数返回 true 如果给定切片在 Unicode 大小写折叠下不相等，则返回 false。它是在字节包下定义的，所以您必须在程序中导入字节包才能访问 EqualFold 功能。

**语法:**

```go
func EqualFold(slice_1, slice1_2 []byte) bool
```

此函数的返回类型是 bool 类型。让我们借助例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate how to check
// the given slices are equal or not
package main

import (
    "bytes"
    "fmt"
)

// Main function
func main() {

    // Creating and initializing slices of bytes
    // Using shorthand declaration
    username := []byte{'G', 'E', 'E', 'K', 'S'}
    uinput := []byte{'g', 'e', 'e', 'k', 's'}

    // Checking whether the given slices are equal or not
    // Using EqualFold() function
    res := bytes.EqualFold(username, uinput)

    // Displaying the result, according
    // to the given condition
    if res == true {

        fmt.Println("!..Successfully Matched..!")
    } else {

        fmt.Println("!..Not Matched..!")
    }

}
```

**输出:**

```go
!..Successfully Matched..!
```

**例 2:**

```go
// Go program to illustrate how to check
// the given slices are equal or not
package main

import (
    "bytes"
    "fmt"
)

func main() {

    // Creating and initializing slices of bytes
    // Using shorthand declaration
    slice_1 := []byte{'G', 'E', 'E', 'K', 'S', 'F',
             'o', 'r', 'G', 'E', 'E', 'K', 'S'}

    slice_2 := []byte{'g', 'e', 'e', 'k', 's', 'f',
             'o', 'r', 'g', 'e', 'e', 'k', 's'}

    slice_3 := []byte{'A', 'P', 'P', 'L', 'E'}

    // Checking whether the given
    // slices are equal or not
    // Using EqualFold() function
    res1 := bytes.EqualFold(slice_1, slice_2)
    res2 := bytes.EqualFold(slice_2, slice_3)
    res3 := bytes.EqualFold(slice_3, []byte("apple"))
    res4 := bytes.EqualFold([]byte("Geeks"), []byte("GEEks"))

    // Displaying results
    fmt.Println("Result_1: ", res1)
    fmt.Println("Result_2: ", res2)
    fmt.Println("Result_3: ", res3)
    fmt.Println("Result_4: ", res4)

}
```

**输出:**

```go
Result_1:  true
Result_2:  false
Result_3:  true
Result_4:  true

```