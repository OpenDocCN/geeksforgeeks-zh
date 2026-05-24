# 如何在 Golang 中将符文映射为大写？

> 原文:[https://www . geeksforgeeks . org/如何将符文映射到大写字母 golang/](https://www.geeksforgeeks.org/how-to-map-a-rune-to-uppercase-in-golang/)

符文是 ASCII 的超集或者是 int32 的别名。它保存了世界书写系统中所有可用的字符，包括重音符号和其他发音符号、制表符和回车等控制代码，并为每个字符分配了一个标准数字。在围棋语言中，这个标准数字被称为 Unicode 码位或符文。
可以借助 **ToUpper()** 功能将给定符文映射到大写。该函数将给定符文的大小写(如果符文的大小写是小写或标题)更改为大写，如果给定符文已经以大写出现，则该函数不执行任何操作。该函数是在 Unicode 包下定义的，因此要访问该方法，您需要在程序中导入 Unicode 包。

**语法:**

```go
func ToUpper(r rune) rune
```

**示例:**

```go
// Go program to illustrate how to
// Map a rune to Uppercase
package main

import (
    "fmt"
    "unicode"
)

// Main function
func main() {

    // Creating rune
    rune_1 := 'G'
    rune_2 := 'e'
    rune_3 := 'E'
    rune_4 := 'k'

    // Mapping the given rune
    // into upper case
    // Using ToUpper() function
    fmt.Printf("Result 1: %c ", unicode.ToUpper(rune_1))
    fmt.Printf("\nResult 2: %c ", unicode.ToUpper(rune_2))
    fmt.Printf("\nResult 3: %c ", unicode.ToUpper(rune_3))
    fmt.Printf("\nResult 4: %c ", unicode.ToUpper(rune_4))
    fmt.Printf("\nResult 5: %c ", unicode.ToUpper('s'))

}
```

**输出:**

```go
Result 1: G 
Result 2: E 
Result 3: E 
Result 4: K 
Result 5: S 

```