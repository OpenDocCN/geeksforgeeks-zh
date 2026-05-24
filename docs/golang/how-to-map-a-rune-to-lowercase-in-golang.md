# 如何在 Golang 中将符文映射为小写？

> 原文:[https://www . geesforgeks . org/如何将符文映射到小写字母 golang/](https://www.geeksforgeeks.org/how-to-map-a-rune-to-lowercase-in-golang/)

符文是 ASCII 的超集或者是 int32 的别名。它保存了世界书写系统中所有可用的字符，包括重音符号和其他发音符号、制表符和回车等控制代码，并为每个字符分配了一个标准数字。在围棋语言中，这个标准数字被称为 Unicode 码位或符文。
可以借助 **ToLower()** 功能将给定符文映射到小写。该函数将给定符文的大小写(如果符文的大小写是大写或小写)更改为小写，如果给定符文已经以小写出现，则该函数不执行任何操作。该函数是在 Unicode 包下定义的，因此要访问该方法，您需要在程序中导入 Unicode 包。

**语法:**

```go
func ToLower(r rune) rune
```

**例 1:**

```go
// Go program to illustrate how
// to map a rune to Lowercase
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
    rune_5 := 's'

    // Mapping the given rune
    // into lower case
    // Using ToLower() function
    fmt.Printf("Result 1: %c ", unicode.ToLower(rune_1))
    fmt.Printf("\nResult 2: %c ", unicode.ToLower(rune_2))
    fmt.Printf("\nResult 3: %c ", unicode.ToLower(rune_3))
    fmt.Printf("\nResult 4: %c ", unicode.ToLower(rune_4))
    fmt.Printf("\nResult 5: %c ", unicode.ToLower(rune_5))
}
```

**输出:**

```go
Result 1: g 
Result 2: e 
Result 3: e 
Result 4: k 
Result 5: s 
Result 6: f 

```

**例 2:**

```go
// Go program to illustrate how
// to map a rune to Lowercase
package main

import (
    "fmt"
    "unicode"
)

// Main function
func main() {

    // Creating rune
    rune_1 := 'S'
    rune_2 := 'a'
    rune_3 := 'M'
    rune_4 := 'P'
    rune_5 := 'L'
    rune_6 := 'e'

    // Mapping the given rune
    // into lower case
    // Using ToLower() function
    fmt.Printf("Result 1: %c ", unicode.ToLower(rune_1))
    fmt.Printf("\nResult 2: %c ", unicode.ToLower(rune_2))
    fmt.Printf("\nResult 3: %c ", unicode.ToLower(rune_3))
    fmt.Printf("\nResult 4: %c ", unicode.ToLower(rune_4))
    fmt.Printf("\nResult 5: %c ", unicode.ToLower(rune_5))
    fmt.Printf("\nResult 6: %c ", unicode.ToLower(rune_6))
}
```

**输出:**

```go
Result 1: s 
Result 2: a 
Result 3: m 
Result 4: p 
Result 5: l 
Result 6: e 

```