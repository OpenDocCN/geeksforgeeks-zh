# 检查符文在 Golang 中是否为 Unicode 标点符号

> 原文:[https://www . geeksforgeeks . org/check-if-the-rune-is-a-unicode-标点-字符-非-in-golang/](https://www.geeksforgeeks.org/check-if-the-rune-is-a-unicode-punctuation-character-or-not-in-golang/)

符文是 ASCII 的超集或者是 *int32* 的别名。它保存了世界书写系统中所有可用的字符，包括重音符号和其他发音符号、制表符和回车等控制代码，并为每个字符分配了一个标准数字。在围棋语言中，这个标准数字被称为 Unicode 码位或符文。
您可以借助**ispunt()**功能检查给定的符文是否为 Unicode 标点符号。如果给定的符文是 Unicode 标点字符，此函数返回 true 如果给定的符文不是 Unicode 标点字符，则返回 false。该函数是在 Unicode 包下定义的，因此要访问该方法，您需要在程序中导入 Unicode 包。

**语法:**

```go
func IsPunct(r rune) bool
```

这个函数的返回类型是布尔型的。让我们借助给定的例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how to check the
// given rune is a Unicode punctuation
// character or not
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
    rune_3 := '!'
    rune_4 := ','
    rune_5 := 'S'

    // Checking the given rune is a Unicode 
    // punctuation character or not
    // Using IsPunct() function
    res_1 := unicode.IsPunct(rune_1)
    res_2 := unicode.IsPunct(rune_2)
    res_3 := unicode.IsPunct(rune_3)
    res_4 := unicode.IsPunct(rune_4)
    res_5 := unicode.IsPunct(rune_5)

    // Displaying results
    fmt.Println(res_1)
    fmt.Println(res_2)
    fmt.Println(res_3)
    fmt.Println(res_4)
    fmt.Println(res_5)

}
```

**输出:**

```go
false
false
true
true
false

```

**例 2:**

```go
// Go program to illustrate how to check the
// given rune is a Unicode punctuation
// character or not
package main

import (
    "fmt"
    "unicode"
)

// Main function
func main() {

    // Creating a slice of rune
    val := []rune{'g', 'f', 'G', '#', ',', ':'}

    // Checking each element of the given slice
    // of the rune is a Unicode punctuation 
    // character or not
    // Using IsPunct() function
    for i := 0; i < len(val); i++ {

        if unicode.IsPunct(val[i]) == true {

            fmt.Println("It is a Unicode punctuation character")

        } else {

            fmt.Println("It is not a Unicode punctuation character")
        }
    }
}
```

**输出:**

```go
It is not a Unicode punctuation character
It is not a Unicode punctuation character
It is not a Unicode punctuation character
It is a Unicode punctuation character
It is a Unicode punctuation character
It is a Unicode punctuation character

```