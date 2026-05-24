# 如何使用 strconv。Golang 中的 FormatUint()函数？

> 原文:[https://www . geesforgeks . org/how-用法-strconv-formatuint-function-in-golang/](https://www.geeksforgeeks.org/how-to-use-strconv-formatuint-function-in-golang/)

Go 语言通过 **strconv Package** 提供内置的支持来实现基本数据类型的字符串表示之间的转换。这个包提供了一个 **FormatUint()函数**，用于返回给定基数中 x 的字符串表示，即 2 < =基数< = 36。
这里，结果使用小写字母“a”到“z”表示大于等于 10 的数字值。要访问 FormatUint()函数，您需要借助 import 关键字在程序中导入 strconv Package。

**语法:**

```go
func FormatUint(x uint64, base int) string
```

**参数:**该函数取两个参数，即 x 和 base。

**返回值:**该函数返回给定基数下 x 的字符串表示，即 2 < =基数< = 36。

**例 1:**

```go
// Golang program to illustrate
// strconv.FormatUint() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {
    // Finding the string representation
    // of given value in the given base
    // Using FormatUint() function
    fmt.Println(strconv.FormatUint(11, 2))
    fmt.Println(strconv.FormatUint(24, 10))

}
```

**输出:**

```go
1011
24

```

**例 2:**

```go
// Golang program to illustrate
// strconv.FormatUint() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding the string representation
    // of given value in the given base
    // Using FormatUint() function
    val1 := uint64(25)
    res1 := strconv.FormatUint(val1, 2)
    fmt.Printf("Result 1: %v", res1)
    fmt.Printf("\nType 1: %T", res1)

    val2 := uint64(20)
    res2 := strconv.FormatUint(val2, 16)
    fmt.Printf("\nResult 2: %v", res2)
    fmt.Printf("\nType 2: %T", res2)

}
```

**输出:**

```go
Result 1: 11001
Type 1: string
Result 2: 14
Type 2: string

```