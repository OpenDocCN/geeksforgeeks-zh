# 如何在 Golang 中对整数和字符串使用数组反向排序函数？

> 原文:[https://www . geesforgeks . org/如何使用数组-反向排序-函数-整数和字符串-在 golang/](https://www.geeksforgeeks.org/how-to-use-array-reverse-sort-functions-for-integer-and-strings-in-golang/)

Go 语言提供了基本常量和运行时反射的内置支持实现来操作排序包。 [Golang](https://www.geeksforgeeks.org/golang-tutorial-learn-go-programming-language/) 是功能相互独立运行的能力。借助该功能，我们可以通过导入**【排序】**包轻松对整数和字符串进行排序。基本上，这将按相反的顺序对整数和字符串进行排序。

**语法:**

```go
func Reverse(data Interface) Interface
```

**返回值:**该函数返回 IntSlice 的值和 StringSlice 的值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to show the uses of
// Integer Reverse Sort Function

package main

import (
    "fmt"
    "sort"
)

func main() {

    fmt.Println("Example For Integer Reverse Sort")

    num := []int{70, 80, 20, 50, 10}

    // using the function
    sort.Sort(sort.Reverse(sort.IntSlice(num)))
    fmt.Println(num)

}
```

**输出:**

```go
Example For Integer Reverse Sort
[80 70 50 20 10]

```

**例 2:**

```go
// Golang program to show the uses of
// String Reverse Sort Function

package main

import (
    "fmt"
    "sort"
)

func main() {

    fmt.Println("Example For String Reverse Sort")

    str:= []string{"GFG","Rank","India","Amid","Covid19"}

    // using the function
    sort.Sort(sort.Reverse(sort.StringSlice(str)))
    fmt.Println(str)

}
```

**输出:**

```go
Example For String Reverse Sort
[Rank India GFG Covid19 Amid]

```