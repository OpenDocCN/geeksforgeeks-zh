# 如何使用 strconv。Golang 中的 FormatBool()函数？

> 原文:[https://www . geesforgeks . org/how-用法-strconv-format bool-function-in-golang/](https://www.geeksforgeeks.org/how-to-use-strconv-formatbool-function-in-golang/)

Go 语言通过 **strconv Package** 提供内置的支持来实现基本数据类型的字符串表示之间的转换。这个包提供了一个 **FormatBool()函数**，用于根据 x 的值返回真或假，要访问 FormatBool()函数，需要借助 import 关键字在程序中导入 strconv Package。

**语法:**

```go
func FormatBool(x bool) string
```

**参数:**该函数取 bool 类型的一个参数，即 x。

**返回值:**该函数根据 x 的值返回真或假。

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate
// strconv.FormatBool() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding true or false
    // according to the input value
    // Using FormatBool() function
    fmt.Println(strconv.FormatBool(true))
    fmt.Println(strconv.FormatBool(false))

}
```

**输出:**

```go
true
false

```

**例 2:**

```go
// Golang program to illustrate
// strconv.FormatBool() Function

package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding true or false
    // according to the input value
    // Using FormatBool() function
    val1 := true
    res1 := strconv.FormatBool(val1)
    fmt.Printf("Result 1: %v", res1)
    fmt.Printf("\nType 1: %T", res1)

    val2 := false
    res2 := strconv.FormatBool(val2)
    fmt.Printf("\nResult 2: %v", res2)
    fmt.Printf("\nType 2: %T", res2)

}
```

**输出:**

```go
Result 1: true
Type 1: string
Result 2: false
Type 2: string

```