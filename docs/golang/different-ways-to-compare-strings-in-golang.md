# 在 Golang 中比较字符串的不同方式

> 原文:[https://www . geesforgeks . org/golang 中字符串比较的不同方法/](https://www.geeksforgeeks.org/different-ways-to-compare-strings-in-golang/)

在 Go 语言中，字符串是用 [UTF-8](https://en.wikipedia.org/wiki/UTF-8) 编码的不可变的任意字节链。您可以使用两种不同的方式来比较字符串:

**1。使用比较运算符:** Go 字符串支持比较运算符，即 *==，！=，> =，< =，<，>* 。在这里， **==** 和**！=** 运算符用于检查给定字符串是否相等，> =，< =，<，>运算符用于查找词法顺序。这些运算符的结果是布尔类型的，这意味着如果满足条件，它将返回*真*，否则，返回*假*。

**例 1:**

## 去

```go
// Go program to illustrate the concept
// of == and != operator with strings
package main

import "fmt"

// Main function
func main() {

    // Creating and initializing strings
    // using shorthand declaration
    str1 := "Geeks"
    str2 := "Geek"
    str3 := "GeeksforGeeks"
    str4 := "Geeks"

    // Checking the string are equal
    // or not using == operator
    result1 := str1 == str2
    result2 := str2 == str3
    result3 := str3 == str4
    result4 := str1 == str4

    fmt.Println("Result 1: ", result1)
    fmt.Println("Result 2: ", result2)
    fmt.Println("Result 3: ", result3)
    fmt.Println("Result 4: ", result4)

    // Checking the string are not equal
    // using != operator
    result5 := str1 != str2
    result6 := str2 != str3
    result7 := str3 != str4
    result8 := str1 != str4

    fmt.Println("\nResult 5: ", result5)
    fmt.Println("Result 6: ", result6)
    fmt.Println("Result 7: ", result7)
    fmt.Println("Result 8: ", result8)

}
```

**输出:**

```go
Result 1:  false
Result 2:  false
Result 3:  false
Result 4:  true

Result 5:  true
Result 6:  true
Result 7:  true
Result 8:  false

```

**例 2:**

## 去

```go
// Go program to illustrate the concept
// of comparison operator with strings
package main

import "fmt"

// Main function
func main() {

    // Creating and initializing
    // slice of string using the
    // shorthand declaration
    myslice := []string{"Geeks", "Geeks",
                    "gfg", "GFG", "for"}

    fmt.Println("Slice: ", myslice)

    // Using comparison operator
    result1 := "GFG" > "Geeks"
    fmt.Println("Result 1: ", result1)

    result2 := "GFG" < "Geeks"
    fmt.Println("Result 2: ", result2)

    result3 := "Geeks" >= "for"
    fmt.Println("Result 3: ", result3)

    result4 := "Geeks" <= "for"
    fmt.Println("Result 4: ", result4)

    result5 := "Geeks" == "Geeks"
    fmt.Println("Result 5: ", result5)

    result6 := "Geeks" != "for"
    fmt.Println("Result 6: ", result6)

}
```

**输出:**

```go
Slice:  [Geeks Geeks gfg GFG for]
Result 1:  false
Result 2:  true
Result 3:  false
Result 4:  true
Result 5:  true
Result 6:  true

```

**2。使用 compare()方法:**还可以使用字符串包提供的内置函数 Compare()来比较两个字符串。此函数在按字典顺序比较两个字符串后返回一个整数值。返回值为:

*   如果 *str1 == str2* ，则返回 0。
*   如果 *str1 > str2* ，返回 1。
*   返回-1，如果 *str1 < str2* 。

**语法:**

```go
func Compare(str1, str2 string) int

```

**示例:**

## 去

```go
// Go program to illustrate how to compare
// string using compare() function
package main

import (
    "fmt"
    "strings"
)

func main() {

    // Comparing string using Compare function
    fmt.Println(strings.Compare("gfg", "Geeks"))

    fmt.Println(strings.Compare("GeeksforGeeks",
                               "GeeksforGeeks"))

    fmt.Println(strings.Compare("Geeks", " GFG"))

    fmt.Println(strings.Compare("GeeKS", "GeeKs"))

}
```

**输出:**

```go
1
0
1
-1

```