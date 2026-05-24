# 如何在 Golang 中加入字节片的元素？

> 原文:[https://www . geeksforgeeks . org/如何加入 golang 中的字节片元素/](https://www.geeksforgeeks.org/how-to-join-the-elements-of-the-byte-slice-in-golang/)

在 Go 语言中[切片](https://www.geeksforgeeks.org/slices-in-golang/)比一个[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一个轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在字节的 Go 切片中，可以借助 ***Join()*** 功能加入字节切片的元素。或者换句话说，Join 函数用于连接切片的元素，并返回一个新的字节切片，该切片包含由给定分隔符分隔的所有这些连接的元素。它是在字节包下定义的，所以您必须在程序中导入字节包来访问连接函数。

**语法:**

```go
func Join(slice_1 [][]byte, sep []byte) []byte
```

这里， *sep* 是放置在结果切片的元素之间的分隔符。让我们借助例子来讨论这个概念:

**例 1:**

```go
// Simple Go program to illustrate
// how to join a slice of bytes
package main

import (
    "bytes"
    "fmt"
)

// Main function
func main() {

    // Creating and initializing
    // slices of bytes
    // Using shorthand declaration
    name := [][]byte{[]byte("Sumit"), 
                     []byte("Kumar"), 
                     []byte("Singh")}
    sep := []byte("-")

    // displaying name of the student in parts
    fmt.Printf("First Name: %s", name[0])
    fmt.Printf("\nMiddle Name: %s", name[1])
    fmt.Printf("\nLast Name: %s", name[2])

    // Join the first, middle, and
    // last name of the student
    // Using Join function
    full_name := bytes.Join(name, sep)

    // Displaying the name of the student
    fmt.Printf("\n\nFull name of the student: %s", full_name)

}
```

**输出:**

```go
First Name: Sumit
Middle Name: Kumar
Last Name: Singh

Full name of the student: Sumit-Kumar-Singh

```

**例 2:**

```go
// Go program to illustrate how to
// join the slices of bytes
package main

import (
    "bytes"
    "fmt"
)

// Main function
func main() {

    // Creating and initializing slices of bytes
    // Using shorthand declaration
    slice_1 := [][]byte{[]byte("Geeks"), []byte("for"), []byte("Geeks")}

    slice_2 := [][]byte{[]byte("Hello"), []byte("My"),
        []byte("name"), []byte("is"), []byte("Bongo")}

    // Displaying slices
    fmt.Println("Slice(Before):")
    fmt.Printf("Slice 1: %s ", slice_1)
    fmt.Printf("\nSlice 2: %s", slice_2)

    // Joining the elements of the slice
    // Using Join function
    res1 := bytes.Join(slice_1, []byte(" , "))
    res2 := bytes.Join(slice_2, []byte(" * "))
    res3 := bytes.Join([][]byte{[]byte("Hey"), []byte("I"), 
              []byte("am"), []byte("Apple")}, []byte("+"))

    // Displaying results
    fmt.Println("\n\nSlice(after):")
    fmt.Printf("New Slice_1: %s ", res1)
    fmt.Printf("\nNew Slice_2: %s", res2)
    fmt.Printf("\nNew Slice_3: %s", res3)

}
```

**输出:**

```go
Slice(Before):
Slice 1: [Geeks for Geeks] 
Slice 2: [Hello My name is Bongo]

Slice(after):
New Slice_1: Geeks , for , Geeks 
New Slice_2: Hello * My * name * is * Bongo
New Slice_3: Hey+I+am+Apple

```