# 如何在戈朗将符文映射到题格？

> 原文:[https://www . geesforgeks . org/如何将符文映射到 golang 中的标题案例/](https://www.geeksforgeeks.org/how-to-map-a-rune-to-title-case-in-golang/)

符文是 ASCII 的超集或者是 int32 的别名。它保存了世界书写系统中所有可用的字符，包括重音符号和其他发音符号、制表符和回车等控制代码，并为每个字符分配了一个标准数字。在围棋语言中，这个标准数字被称为 Unicode 码位或符文。
你可以借助**totile()**功能将给定符文映射到题格中。该函数将给定符文的大小写(如果符文的大小写是较低或较高)更改为标题大小写，如果给定符文已经出现在标题大小写中，则该函数不执行任何操作。该函数是在 Unicode 包下定义的，因此要访问该方法，您需要在程序中导入 Unicode 包。

**语法:**

```go
func ToTitle(r rune) rune
```

**例 1:**

```go
// Go program to illustrate how to
// map a rune to title case
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
    rune_3 := 'E'
    rune_4 := 'k'

    // Mapping the given rune into title case
    // Using ToTitle() function
    fmt.Printf("Result 1: %c ", unicode.ToTitle(rune_1))
    fmt.Printf("\nResult 2: %c ", unicode.ToTitle(rune_2))
    fmt.Printf("\nResult 3: %c ", unicode.ToTitle(rune_3))
    fmt.Printf("\nResult 4: %c ", unicode.ToTitle(rune_4))
    fmt.Printf("\nResult 5: %c ", unicode.ToTitle('s'))

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

**例 2:**

```go
// Go program to illustrate how to
// map a rune to title case
package main

import (
    "fmt"
    "unicode"
)

// Main function
func main() {

    // Creating rune
    rune_1 := 'r'
    rune_2 := 'U'
    rune_3 := 'n'
    rune_4 := 'E'

    // Mapping the given rune into title case
    // Using ToTitle() function
    fmt.Printf("Result 1: %c ", unicode.ToTitle(rune_1))
    fmt.Printf("\nResult 2: %c ", unicode.ToTitle(rune_2))
    fmt.Printf("\nResult 3: %c ", unicode.ToTitle(rune_3))
    fmt.Printf("\nResult 4: %c ", unicode.ToTitle(rune_4))    

}
```

**输出:**

```go
Result 1: R 
Result 2: U 
Result 3: N 
Result 4: E 

```