# 检查指定的元素是否出现在 Golang

的字节片段中

> 原文:[https://www . geeksforgeeks . org/check-如果指定的元素存在于 golang 字节片中/](https://www.geeksforgeeks.org/check-if-the-specified-element-is-present-in-the-slice-of-bytes-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。在转到字节切片中，可以使用以下函数检查给定切片是否包含指定元素。这些函数是在字节包下定义的，所以您必须在程序中导入字节包来访问这些函数。

**1。包含:**该函数用于检查指定元素在给定的字节片段中是否存在。如果元素存在于切片中，此方法返回*真*，如果元素不存在于给定切片中，则返回*假*。

**语法:**

```go
func Contains(slice_1, sub_slice []byte) bool
```

**示例:**

```go
// Go program to illustrate how to check the
// slice contains the specified element in it
package main

import (
    "bytes"
    "fmt"
)

func main() {

    // Creating and initializing
    // slice of bytes
    // Using shorthand declaration
    slice_1 := []byte{'A', 'N', 'M',
                      'O', 'P', 'Q'}

    // Checking the slice
    // using Contains function
    res1 := bytes.Contains(slice_1, []byte{'A'})
    res2 := bytes.Contains(slice_1, []byte{'x'})
    res3 := bytes.Contains([]byte("GeeksforGeeks"), []byte("ks"))
    res4 := bytes.Contains([]byte("Geeks"), []byte(""))
    res5 := bytes.Contains([]byte(""), []byte(""))

    // Displaying results
    fmt.Println("Result 1:", res1)
    fmt.Println("Result 2:", res2)
    fmt.Println("Result 3:", res3)
    fmt.Println("Result 4:", res4)
    fmt.Println("Result 5:", res5)

}
```

**输出:**

```go
Result 1: true
Result 2: false
Result 3: true
Result 4: true
Result 5: true

```

**2。ContainsAny:** 此函数用于检查给定的字节片段中是否存在字符中的任何 UTF-8 编码码点。如果片内存在字符中的任何 UTF-8 编码码点，此方法返回 true 如果给定片内存在字符中的任何 UTF-8 编码码点，此方法返回 false。

**语法:**

```go
func ContainsAny(slice_1 []byte, charstr string) bool
```

**示例:**

```go
// Go program to illustrate how to check the
// slice contain the specified string in it
package main

import (
    "bytes"
    "fmt"
)

func main() {

    // Creating and initializing
    // slice of bytes
    // Using shorthand declaration

    slice_1 := []byte{'A', 'N', 'M', 'O', 'P', 'Q'}

    // Checking the slice
    // Using ContainsAny function
    res1 := bytes.ContainsAny(slice_1, "A")
    res2 := bytes.ContainsAny(slice_1, "a")
    res3 := bytes.ContainsAny([]byte("GeeksforGeeks"), "ksjkd")
    res4 := bytes.ContainsAny([]byte("Geeks"), "")
    res5 := bytes.ContainsAny([]byte(""), "")

    // Displaying results
    fmt.Println("Result 1:", res1)
    fmt.Println("Result 2:", res2)
    fmt.Println("Result 3:", res3)
    fmt.Println("Result 4:", res4)
    fmt.Println("Result 5:", res5)

}
```

**输出:**

```go
Result 1: true
Result 2: false
Result 3: true
Result 4: false
Result 5: false

```