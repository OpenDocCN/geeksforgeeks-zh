# Golang |在指定的分隔符后分割切片

> 原文:[https://www . geesforgeks . org/golang-在指定分隔符后拆分切片/](https://www.geeksforgeeks.org/golang-splitting-the-slice-after-the-specified-separator/)

In Go 语言切片比数组更强大、灵活、方便，是一种轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。
在字节的 Go 切片中，您可以使用 **SplitAfterN()** 函数在指定的分隔符后分割切片。此函数在给定分隔符的每个实例之后将一个切片拆分为所有子切片，并返回包含这些子切片的切片。如果给定的分隔符是空的，那么它在每个 UTF-8 序列之后拆分，并且计数指示要返回的子片段的数量。它是在字节包下定义的，所以你必须在程序中导入字节包来访问 SplitAfterN 函数。

**语法:**

```go
func SplitAfterN(o_slice, sep []byte, m int) [][]byte
```

这里， **o_slice** 是原始字符串，sep 是分隔符，m 用来查找要返回的子字符串个数。这里如果 **m > 0** ，那么最多返回 m 个子虱子，最后一串子虱子不会分裂。如果 **m == 0** ，则返回零。如果 **m < 0** ，则返回所有子策略。让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate the concept 
// of splitting a slice of bytes 
package main 

import ( 
    "bytes"
    "fmt"
) 

func main() { 

    // Creating and Splitting  
    // the slice of bytes 
    // Using SplitAfterN function 
    res1 := bytes.SplitAfterN([]byte("****Welcome, to, GeeksforGeeks****"), 
                                                           []byte(","), -1) 

    res2 := bytes.SplitAfterN([]byte("Learning x how x to x "+
                 "trim x a x slice of bytes"), []byte("x"), 3) 

    res3 := bytes.SplitAfterN([]byte("Geeks,for,Geeks, Geek"), []byte(","), 0) 

    res4 := bytes.SplitAfterN([]byte(""), []byte(","), 2) 

    // Display the results 
    fmt.Printf("\nFinal Result after splitting:\n") 
    fmt.Printf("\nSlice 1: %s", res1) 
    fmt.Printf("\nSlice 2: %s", res2) 
    fmt.Printf("\nSlice 3: %s", res3) 
    fmt.Printf("\nSlice 4: %s", res4) 
} 
```

**输出:**

```go
Final Result after splitting:

Slice 1: [****Welcome,  to,  GeeksforGeeks****]
Slice 2: [Learning x  how x  to x trim x a x slice of bytes]
Slice 3: []
Slice 4: []

```

**例 2:**

```go
// Go program to illustrate the concept 
// of splitting a slice of bytes 
package main 

import ( 
    "bytes"
    "fmt"
) 

func main() { 

    // Creating and initializing 
    // the slice of bytes 
    // Using shorthand declaration 
    slice_1 := []byte{'!', '!', 'G', 'e', 'e', 'k', 's', 'f', 'o', 'r',
            'G', 'e', 'e', 'k', 's', 'G', 'e', 'e', 'k', 's', '#', '#'} 

    slice_2 := []byte{'A', 'p', 'p','p','p','l', 'e'} 

    slice_3 := []byte{'%', 'g', '%', 'e', '%',  
                 'e', '%', 'k', '%', 's', '%'} 

    // Displaying slices 
    fmt.Println("Original Slice:") 
    fmt.Printf("Slice 1: %s", slice_1) 
    fmt.Printf("\nSlice 2: %s", slice_2) 
    fmt.Printf("\nSlice 3: %s", slice_3) 

    // Splitting the slice of bytes 
    // Using SplitAfterN function 
    res1 := bytes.SplitAfterN(slice_1, []byte("eek"), 2) 
    res2 := bytes.SplitAfterN(slice_2, []byte(""), 3) 
    res3 := bytes.SplitAfterN(slice_3, []byte("%"), 0) 

    // Display the results 
    fmt.Printf("\n\nAfter splitting:\n") 
    fmt.Printf("\nSlice 1: %s", res1) 
    fmt.Printf("\nSlice 2: %s", res2) 
    fmt.Printf("\nSlice 3: %s", res3) 

} 
```

**输出:**

```go
Original Slice:
Slice 1: !!GeeksforGeeksGeeks##
Slice 2: Apppple
Slice 3: %g%e%e%k%s%

After splitting:

Slice 1: [!!Geek sforGeeksGeeks##]
Slice 2: [A p ppple]
Slice 3: []

```