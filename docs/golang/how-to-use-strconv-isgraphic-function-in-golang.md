# 如何使用 strconv。Golang 中的 IsGraphic()函数？

> 原文:[https://www . geesforgeks . org/how-用法-strconv-is graphic-function-in-golang/](https://www.geeksforgeeks.org/how-to-use-strconv-isgraphic-function-in-golang/)

Go 语言通过 **strconv Package** 提供内置的支持来实现基本数据类型的字符串表示之间的转换。这个包提供了一个 **IsGraphic()函数**，用来检查符文是否被 Unicode 定义为图形。
这种类型的字符包括字母、标记、数字、标点、符号和空格，来自 L、M、N、P、S 和 Zs 类别。要访问 IsGraphic()函数，您需要借助 import 关键字在程序中导入 strconv Package。

**语法:**

```go
func IsGraphic(x rune) bool
```

**参数:**该函数取符文类型的一个参数，即 x。

**返回值:**如果符文被 Unicode 定义为图形，则该函数返回 true。否则，返回 false。

**例 1:**

```go
// Golang program to illustrate 
// strconv.IsGraphic() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Checking whether the rune is 
    // defined as a Graphic by Unicode
    // Using IsGraphic() function
    fmt.Println (strconv.IsGraphic('♥'))
    fmt.Println (strconv.IsGraphic('b'))

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
// strconv.IsGraphic() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Checking whether the rune
    // is defined as a Graphic by Unicode
    // Using IsGraphic() function
    val1 := 'a'
    res1 := strconv.IsGraphic(val1)
    fmt.Printf("Result 1: %v", res1)

    val2 := '♦'
    res2 := strconv.IsGraphic(val2)
    fmt.Printf("\nResult 2: %v", res2)

    val3 := '\001'
    res3 := strconv.IsGraphic(val3)
    fmt.Printf("\nResult 3: %v", res3) 
}

```

**输出:**

```go
Result 1: true
Result 2: true
Result 3: false

```