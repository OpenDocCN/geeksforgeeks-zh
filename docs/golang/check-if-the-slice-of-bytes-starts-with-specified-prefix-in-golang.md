# 检查字节片是否以 Golang

中指定的前缀开始

> 原文:[https://www . geesforgeks . org/check-if-the-slice-of-bytes-start-with-specified-prefix-in-golang/](https://www.geeksforgeeks.org/check-if-the-slice-of-bytes-starts-with-specified-prefix-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在字节的 Go 切片中，可以借助 ***HasPrefix** ()* 功能检查给定切片是否以指定前缀开头。如果给定切片以指定前缀开头，则该函数返回 true 如果给定切片不以指定前缀开头，则返回 false。它是在字节包下定义的，所以您必须在程序中导入字节包来访问 HasPrefix 函数。

**语法:**

```go
func HasPrefix(slice_1, pre []byte) bool
```

这里， *slice_1* 是字节的原始切片，pre 是前缀，也是字节的切片。此函数的返回类型是 bool 类型。让我们借助一个例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how to check the
// given slice starts with the specified prefix
package main

import (
    "bytes"
    "fmt"
)

func main() {

    // Creating and initializing
    // slice of bytes
    // Using shorthand declaration
    slice_1 := []byte{'G', 'E', 'E', 'K', 'S', 'F',
                 'o', 'r', 'G', 'E', 'E', 'K', 'S'}

    slice_2 := []byte{'A', 'P', 'P', 'L', 'E'}

    // Checking whether the given slice starts 
    // with the specified prefix or not
    // Using  HasPrefix () function
    res1 := bytes.HasPrefix(slice_1, []byte("G"))
    res2 := bytes.HasPrefix(slice_2, []byte("O"))
    res3 := bytes.HasPrefix([]byte("Hello! I am Apple."), []byte("Hello"))
    res4 := bytes.HasPrefix([]byte("Hello! I am Apple."), []byte("Welcome"))
    res5 := bytes.HasPrefix([]byte("Hello! I am Apple."), []byte("H"))
    res6 := bytes.HasPrefix([]byte("Hello! I am Apple."), []byte("X"))
    res7 := bytes.HasPrefix([]byte("Geeks"), []byte(""))

    // Displaying results
    fmt.Println("Result_1: ", res1)
    fmt.Println("Result_2: ", res2)
    fmt.Println("Result_3: ", res3)
    fmt.Println("Result_4: ", res4)
    fmt.Println("Result_5: ", res5)
    fmt.Println("Result_6: ", res6)
    fmt.Println("Result_7: ", res7)

}
```

**输出:**

```go
Result_1:  true
Result_2:  false
Result_3:  true
Result_4:  false
Result_5:  true
Result_6:  false
Result_7:  true

```