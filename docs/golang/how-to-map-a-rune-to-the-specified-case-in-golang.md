# 如何将一个符文映射到戈朗的指定格？

> 原文:[https://www . geesforgeks . org/如何将符文映射到指定的 golang 案例/](https://www.geeksforgeeks.org/how-to-map-a-rune-to-the-specified-case-in-golang/)

符文是 ASCII 的超集或者是 int32 的别名。它保存了世界书写系统中所有可用的字符，包括重音符号和其他发音符号、制表符和回车等控制代码，并为每个字符分配了一个标准数字。在围棋语言中，这个标准数字被称为 Unicode 码位或符文。
可以借助 **To()** 功能将符文映射到指定的格。这个功能会根据你的要求把给定符文的大小写改成小写，大写，或者标题大小写。如果给定的符文已经出现在指定的情况下，那么这个函数什么也不做。该函数是在 Unicode 包下定义的，因此要访问该方法，您需要在程序中导入 Unicode 包。

**语法:**

```go
func To(_case int, r rune) rune
```

**例 1:**

```go
// Go program to illustrate how to
// map a rune to the specified case
package main

import (
    "fmt"
    "unicode"
)

// Main function
func main() {

    // Creating rune
    rune_1 := 'g'
    rune_2 := 'e'

    // Mapping the given rune 
    // into the specified case
    // Using To() function
    fmt.Printf("Result 1: %c ", unicode.To(unicode.UpperCase, rune_1))
    fmt.Printf("\nResult 2: %c ", unicode.To(unicode.TitleCase, rune_2))

}
```

**输出:**

```go
Result 1: G 
Result 2: E

```

**例 2:**

```go
// Go program to illustrate how to
// map a rune to the specified case
package main

import (
    "fmt"
    "unicode"
)

// Main function
func main() {

    // Creating rune
    rune_1 := 'E'
    rune_2 := 'K'

    // Mapping the given rune 
    // into the specified case
    // Using To() function
    fmt.Printf("\nResult 1: %c ", unicode.To(unicode.LowerCase, rune_1))
    fmt.Printf("\nResult 2: %c ", unicode.To(unicode.TitleCase, rune_2))
    fmt.Printf("\nResult 3: %c ", unicode.To(unicode.UpperCase, 's'))

}
```

**输出:**

```go
Result 1: e 
Result 2: K 
Result 3: S 

```