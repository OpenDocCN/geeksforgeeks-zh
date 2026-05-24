# 如何使用 strconv。Golang 中的 IsPrint()函数？

> 原文:[https://www . geeksforgeeks . org/使用方法-strconv-is print-function-in-golang/](https://www.geeksforgeeks.org/how-to-use-strconv-isprint-function-in-golang/)

Go 语言通过 **strconv Package** 提供内置的支持来实现基本数据类型的字符串表示之间的转换。这个包提供了一个 **IsPrint()函数**，用来检查符文是否定义为 Go 可打印，定义是否与 unicode 相同。是字母、数字、标点、符号和 ASCII 空格的打印。要访问 IsPrint()函数，您需要借助 import 关键字在程序中导入 strconv Package。

**语法:**

```go
func IsPrint(x rune) bool
```

**参数:**该函数取符文类型的一个参数，即 x。

**返回值:**如果符文被 Unicode 定义为图形，则该函数返回 true。否则，返回 false。

**例 1:**

```go
// Golang program to illustrate
// strconv.IsPrint() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Checking whether the rune
    // is defined as printable by Go
    // Using IsPrint() function
    fmt.Println(strconv.IsPrint('?'))
    fmt.Println(strconv.IsPrint('b'))

}
```

**输出:**

```go
true
true

```

**例 2:**

```go
// Golang program to illustrate
// strconv.IsPrint() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Checking whether the rune 
    // is defined as printable by Go
    // Using IsPrint() function
    val1 := 'a'
    res1 := strconv.IsPrint(val1)
    fmt.Printf("Result 1: %v", res1)

    val2 := '?'
    res2 := strconv.IsPrint(val2)
    fmt.Printf("\nResult 2: %v", res2)

    val3 := '\001'
    res3 := strconv.IsPrint(val3)
    fmt.Printf("\nResult 3: %v", res3)

}
```

**输出:**

```go
Result 1: true
Result 2: true
Result 3: false

```