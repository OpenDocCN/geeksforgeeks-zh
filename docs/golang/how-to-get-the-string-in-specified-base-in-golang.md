# 如何在 Golang 中获取指定基数的字符串？

> 原文:[https://www . geeksforgeeks . org/如何获取指定碱基字符串 in-golang/](https://www.geeksforgeeks.org/how-to-get-the-string-in-specified-base-in-golang/)

Go 语言通过 *strconv Package* 提供内置的支持来实现基本数据类型的字符串表示之间的转换。这个包提供了一个 **FormatInt()函数**，用于返回给定基数中 x 的字符串表示，即 2 < =基数< = 36。
这里，结果使用小写字母“a”到“z”表示大于等于 10 的数字值。要访问 FormatInt()函数，您需要借助 import 关键字在程序中导入 strconv Package。

**语法:**

```go
func FormatInt(x int64, base int) string
```

**参数:**该函数取两个参数，即 x 和 base。

**返回值:**该函数返回给定基数下 x 的字符串表示，即 2 < =基数< = 36。

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate
// strconv.FormatInt() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {
    // Finding the string representation
    // of given value in the given base
    // Using FormatInt() function
    fmt.Println(strconv.FormatInt(23, 2))
    fmt.Println(strconv.FormatInt(-24, 10))

}
```

**输出:**

```go
10111
-24

```

**例 2:**

```go
// Golang program to illustrate
// strconv.FormatInt() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding the string representation
    // of given value in the given base
    // Using FormatInt() function
    val1 := int64(25)
    res1 := strconv.FormatInt(val1, 2)
    fmt.Printf("Result 1: %v", res1)
    fmt.Printf("\nType 1: %T", res1)

    val2 := int64(-50)
    res2 := strconv.FormatInt(val2, 16)
    fmt.Printf("\nResult 2: %v", res2)
    fmt.Printf("\nType 2: %T", res2)

}
```

**输出:**

```go
Result 1: 11001
Type 1: string
Result 2: -32
Type 2: string

```