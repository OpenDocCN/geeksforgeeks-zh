# 如何在 Golang 中重复一片字节？

> 原文:[https://www . geesforgeks . org/如何在 golang 中重复一个字节片/](https://www.geeksforgeeks.org/how-to-repeat-a-slice-of-bytes-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在字节的 Go 切片中，您可以借助 *Repeat()* 功能将切片的元素重复特定次数。此方法返回一个包含切片重复元素的新字符串。它是在字节包下定义的，所以你必须在程序中导入字节包来访问重复函数。

**语法:**

```go
func Repeat(slice_1 []byte, count int) []byte
```

这里， *slice_1* 代表字节的切片，计数值代表您想要重复给定的 *slice_1* 的元素的次数。

**示例:**

```go
// Go program to illustrate how to repeat
// the elements of the slice of bytes
package main

import (
    "bytes"
    "fmt"
)

// Main function
func main() {

    // Creating and initializing
    // the slice of bytes
    // Using shorthand declaration
    slice_1 := []byte{'G', 'E', 'E', 'K', 'S'}
    slice_2 := []byte{'A', 'P', 'P', 'L', 'E'}

    // Repeating the given slice
    // Using Repeat function
    res1 := bytes.Repeat(slice_1, 2)
    res2 := bytes.Repeat(slice_2, 4)
    res3 := bytes.Repeat([]byte("Geeks"), 5)

    // Display the results
    fmt.Printf("Result 1: %s", res1)
    fmt.Printf("\nResult 2: %s", res2)
    fmt.Printf("\nResult 3: %s", res3)
}
```

**输出:**

```go
Result 1: GEEKSGEEKS
Result 2: APPLEAPPLEAPPLEAPPLE
Result 3: GeeksGeeksGeeksGeeksGeeks

```

**注意:**如果计数值为负或者( *len(slice_1) * count* )的结果溢出，该方法会死机。

**示例:**

```go
// Go program to illustrate how to repeat
// the elements of the slice of bytes
package main

import (
    "bytes"
    "fmt"
)

// Main function
func main() {

    // Creating and initializing 
    // the slice of bytes
    // Using shorthand declaration
    slice_1 := []byte{'G', 'E', 'E', 'K', 'S'}
    slice_2 := []byte{'A', 'P', 'P', 'L', 'E'}

    // Repeating the given slice
    // Using Repeat function
    // If we use a negative 
    // value in the count
    // then this function will 
    // panic because negative
    // values are not allowed to count
    res1 := bytes.Repeat(slice_1, -2)
    res2 := bytes.Repeat(slice_2, -4)
    res3 := bytes.Repeat([]byte("Geeks"), -5)

    // Display the results
    fmt.Printf("Result 1: %s", res1)
    fmt.Printf("\nResult 2: %s", res2)
    fmt.Printf("\nResult 3: %s", res3)
}
```

**输出:**

> 死机:字节:负重复计数
> 
> goro tine 1[running]:
> 字节。重复(0x41a787、0x5、0x5、0xfffffffe、0x66ec0、0x3f37、0xf0a40、0x 40 A0 d 0)
> /usr/local/go/src/bytes/bytes . go:485+0x1a 0
> main . main()
> /tmp/沙盒 192154574/prog.go:22 +0x80