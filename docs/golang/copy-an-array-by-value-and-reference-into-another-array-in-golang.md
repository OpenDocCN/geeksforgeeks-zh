# 通过值和引用将一个数组复制到 Golang 的另一个数组中

> 原文:[https://www . geeksforgeeks . org/将一个数组按值和引用复制到另一个数组中/golang/](https://www.geeksforgeeks.org/copy-an-array-by-value-and-reference-into-another-array-in-golang/)

Golang 中的数组是同一类型元素的编号序列。数组的大小是固定的。我们可以通过元素的索引来访问它们。您可以声明一个大小为 n、类型为 T 的数组，如下所述。

```go
var array[n]T 

```

Go 没有将一个数组复制到另一个数组的内置函数。将一个数组复制到另一个数组有两种方式:

*   By value
*   By reference

**1。按值复制:**如果我们按值复制一个数组，然后对原始数组的值进行更改，相同的更改不会反映在原始数组的副本中。

**2。通过引用复制:**如果我们通过引用复制一个数组，然后在原始数组中进行任何更改，那么它们将反映在创建的原始数组的副本中。

**例:**

```go
// Golang program to copy an array by value
// and reference into another array
package main

import "fmt"

func main() {

    // original string
    strArray := [3]string{"Apple", "Mango", "Guava"}

    // data is passed by value
    Arraybyval := strArray

    // data is passed by reference
    Arraybyref := &strArray

    fmt.Printf("strArray: %v\n", strArray)
    fmt.Printf("Arraybyval : %v\n", Arraybyval)
    fmt.Printf("*Arraybyref : %v\n", *Arraybyref)

    strArray[0] = "Watermelon"

    fmt.Printf("After making changes")

    fmt.Printf("strArray: %v\n", strArray)
    fmt.Printf("Arraybyval: %v\n", Arraybyval)
    fmt.Printf("*Arraybyref: %v\n", *Arraybyref)
}
```

**输出:**

```go
strArray: [Apple Mango Guava]
Arraybyval : [Apple Mango Guava]
*Arraybyref : [Apple Mango Guava]
After making changesstrArray: [Watermelon Mango Guava]
Arraybyval: [Apple Mango Guava]
*Arraybyref: [Watermelon Mango Guava]

```