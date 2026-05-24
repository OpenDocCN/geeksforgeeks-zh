# 如何使用 strconv。伊藤()在 Golang 的作用？

> 原文:[https://www . geesforgeks . org/how-用法-strconv-itoa-function-in-golang/](https://www.geeksforgeeks.org/how-to-use-strconv-itoa-function-in-golang/)

Go 语言通过 **strconv Package** 提供内置的支持来实现基本数据类型的字符串表示之间的转换。这个包提供了一个**伊藤()函数**，相当于 FormatInt(int64(x)，10)。或者换句话说，当基数为 10 时，Itoa()函数返回 x 的字符串表示形式。要访问 Itoa()函数，您需要借助 import 关键字在程序中导入 strconv Package。

**语法:**

```go
 func Itoa(x int) string
```

**参数:**该函数取 int 类型的一个参数，即 x。

**返回值:**这个函数返回一个代表 x 的字符串。

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate
// strconv.Itoa() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding a string representation of
    // the given value when the base is 10
    // Using Itoa() function
    fmt.Println(strconv.Itoa(23))
    fmt.Println(strconv.Itoa(45))

}
```

**输出:**

```go
23
45

```

**例 2:**

```go
// Golang program to illustrate
// strconv.Itoa() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Finding a string representation of
    // the given value when the base is 10
    // Using Itoa() function
    val1 := int(24)
    res1 := strconv.Itoa(val1)
    fmt.Printf("Result 1: %v", res1)
    fmt.Printf("\nType 1: %T", res1)

    val2 := int(-21)
    res2 := strconv.Itoa(val2)
    fmt.Printf("\nResult 2: %v", res2)
    fmt.Printf("\nType 2: %T", res2)

}
```

**输出:**

```go
Result 1: 24
Type 1: string
Result 2: -21
Type 2: string

```