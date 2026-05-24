# 如何得到 Golang 中整数的随机排列？

> 原文:[https://www . geeksforgeeks . org/如何获得 golang 中整数的随机排列/](https://www.geeksforgeeks.org/how-to-get-random-permutation-of-integers-in-golang/)

Go 语言在 math/rand 包的帮助下，为生成指定类型的随机数提供了内置支持。这个包实现了伪随机数生成器。这些随机数是由一个源生成的，每当程序运行时，这个源都会产生一个确定性的值序列。而且如果你想将随机数用于安全敏感的工作，那么就使用 crypto/rand 包。

在数学/兰德包提供的 **Perm()函数**的帮助下，您可以从默认源生成一个包含整数[0，n]的非负伪随机排列的 n 个整数片。因此，您需要在导入关键字的帮助下，在程序中添加一个 math/rand 包来访问 Perm()函数。

**语法:**

```go
func Perm(n int) []int
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate
// how to get a random number
package main

import (
    "fmt"
    "math/rand"
)

// Main function
func main() {

    // Getting the random permutation
    // of integers in the form of slice
    // Using Perm() function
    for _, res_1 := range rand.Perm(4) {

        // Displaying the result
        fmt.Println("Slice 1 Element: ", res_1)
    }
    for _, res_2 := range rand.Perm(3) {

        // Displaying the result
        fmt.Println("Slice 2 Element: ", res_2)
    }

}
```

**输出:**

```go
Slice 1 Element:  0
Slice 1 Element:  1
Slice 1 Element:  2
Slice 1 Element:  3
Slice 2 Element:  1
Slice 2 Element:  2
Slice 2 Element:  0

```

**例 2:**

```go
// Golang program to illustrate
// how to get a random permutation
// of integers
package main

import (
    "fmt"
    "math/rand"
)

// Main function
func main() {

    // Getting the random permutation
    // of integers in the form of slice
    // Using Perm() function
    res_1 := rand.Perm(5)
    res_2 := rand.Perm(7)
    fmt.Println("Slice 1: ", res_1)

    // Finding the length of the slice
    fmt.Println("Length of Slice 1: ", len(res_1))

    // Finding the capacity of the slice
    fmt.Println("Capacity of Slice 1: ", cap(res_1))

    fmt.Println("Slice 2: ", res_2)

    // Finding the length of the slice
    fmt.Println("Length of Slice 2: ", len(res_2))

    // Finding the capacity of the slice
    fmt.Println("Capacity of Slice 2: ", cap(res_2))

}
```

**输出:**

```go
Slice 1:  [0 4 2 3 1]
Length of Slice 1:  5
Capacity of Slice 1:  5
Slice 2:  [4 1 5 0 3 2 6]
Length of Slice 2:  7
Capacity of Slice 2:  7

```