# 如何对 Golang 中的 Search 进行切片排序？

> 原文:[https://www . geesforgeks . org/如何对 golang 中的搜索片段进行排序/](https://www.geeksforgeeks.org/how-to-sort-a-slice-of-search-in-golang/)

Go 语言提供了基本常量和运行时反射的内置支持实现来操作排序包。Golang 具有功能相互独立运行的能力。借助该功能，我们可以通过导入**“排序”**包，轻松对整数和字符串进行排序。这些函数是在排序包下定义的，因此您需要在程序中导入排序包。排序函数可以搜索任何重要的 Golang 排序函数列表，如下所示:

**语法:**

```go
func Search(n int, f func(int) bool) int
```

**返回值:**此函数返回[0，n]中 f(i)为真的最小索引 I，假设在范围[0，n]上，f(i) == true 意味着 f(i+1) == true。

此功能仅用于对搜索的一部分进行排序。以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
package main

import (
    "fmt"
    "sort"
)

func main() {

    // integer slice in unsort order
    intSlice := []int{10, 3, 6, 10, 15, 21, 38, 26, 25, 45}
    a := 15
    pos := sort.SearchInts(intSlice, a)
    fmt.Printf("Found %d at index %d in %v\n", a, pos, intSlice)

    // string slice in unsorted order
    strSlice := []string{"Pink", "Orange", 
                         "Green", "Black", 
                  "Purple", "Blue", "Red"}

    b := "Green"
    pos = sort.SearchStrings(strSlice, b)
    fmt.Printf("Found %s at index %d in %v\n",
                             b, pos, strSlice)

    // string slice in unsorted order
    fltSlice := []float64{612.15, 114.510,
               211.144, 396.242, 485.143}

    c := 211.144
    pos = sort.SearchFloat64s(fltSlice, c)
    fmt.Printf("Found %f at index %d in %v\n",
                            c, pos, fltSlice)

    // sorted slice in descending
    d := []int{45, 38, 26, 25, 21, 15, 10, 10, 6, 3}
    e := 38
    i := sort.Search(len(d), func(i int) bool { return d[i] <= e })

    if i < len(d) && d[i] == e {
        fmt.Printf("found %d at index %d in %v\n", e, i, d)
    } else {
        fmt.Printf("%d not found in %v\n", e, d)
    }
}
```

**输出:**

```go
Found 15 at index 4 in [10 3 6 10 15 21 38 26 25 45]
Found Green at index 6 in [Pink Orange Green Black Purple Blue Red]
Found 211.144000 at index 2 in [612.15 114.51 211.144 396.242 485.143]
found 38 at index 1 in [45 38 26 25 21 15 10 10 6 3]

```

**示例 2:** 给定示例说明了搜索以不同形式按升序排序的列表。

```go
package main

import (
    "fmt"
    "sort"
)

func main() {

    // unsorted
    s := []int{19, 42, 24, 63, -20, 59}
    sort.Sort(sort.IntSlice(s))

    // sorted
    fmt.Println(s)
    fmt.Println("Length of Slice: ", sort.IntSlice.Len(s))

    fmt.Println("40 found in Slice at position: ",
        sort.IntSlice(s).Search(40))

    fmt.Println("-10 found in Slice at position: ",
        sort.IntSlice(s).Search(6))
    fmt.Println("-----------------------------------")

    t := []string{"Pink", "Orange", "Green",
        "Black", "Purple", "Blue", "Red"}

    sort.Sort(sort.StringSlice(t))

    fmt.Println(t)
    fmt.Println("Length of Slice: ", sort.StringSlice.Len(t))

    fmt.Println("Black found in Slice at position: ",
        sort.StringSlice(t).Search("Black"))

    fmt.Println("Orange found in Slice at position: ",
        sort.StringSlice(t).Search("Orange"))

    fmt.Println("-----------------------------------")

    // unsorted
    u := []float64{602.15, 194.10, 611.144, 396.42, 655.433}
    sort.Sort(sort.Float64Slice(u))

    // sorted
    fmt.Println(u)
    fmt.Println("Length of Slice: ", sort.Float64Slice.Len(u))

    fmt.Println("611.144 found in Slice at position: ",
        sort.Float64Slice(u).Search(611.144))

    fmt.Println("194.10 found in Slice at position: ",
        sort.Float64Slice(u).Search(194.10))
}
```

**输出:**

```go
[-20 19 24 42 59 63]
Length of Slice:  6
40 found in Slice at position:  3
-10 found in Slice at position:  1
-----------------------------------
[Black Blue Green Orange Pink Purple Red]
Length of Slice:  7
Black found in Slice at position:  0
Orange found in Slice at position:  3
-----------------------------------
[194.1 396.42 602.15 611.144 655.433]
Length of Slice:  5
611.144 found in Slice at position:  3
194.10 found in Slice at position:  0

```