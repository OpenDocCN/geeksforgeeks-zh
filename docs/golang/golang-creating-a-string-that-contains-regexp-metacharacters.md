# Golang |创建包含正则表达式元字符的字符串

> 原文:[https://www . geesforgeks . org/golang-creating-a-string-in-contains-regexp-meta characters/](https://www.geeksforgeeks.org/golang-creating-a-string-that-contains-regexp-metacharacters/)

正则表达式是定义搜索模式的字符序列。Go 语言支持正则表达式。正则表达式用于解析、过滤、验证和从大文本中提取有意义的信息，如日志、其他程序生成的输出等。
在 Go regexp 中，允许在 **QuoteMeta()** 函数的帮助下，创建一个转义指定文本中所有正则表达式元字符的字符串。该函数返回的字符串是与文本匹配的正则表达式。这个函数是在 regexp 包下定义的，所以要访问这个方法，你需要在程序中导入 regexp 包。

**语法:**

```go
func QuoteMeta(str string) string
```

**例 1:**

```go
// Go program to illustrate how to create
// a string that escapes all regular
// expression metacharacters
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Escaping all regular
    // expression metacharacters
    // Using QuoteMeta () function
    res1 := regexp.QuoteMeta(`String 1: .+*()|[]{}^
 Golang |创建包含正则表达式元字符的字符串
)
    fmt.Println(res1)

    res2 := regexp.QuoteMeta(`String 2: +()*`)
    fmt.Println(res2)

    res3 := regexp.QuoteMeta(`String 3: []|{}
 Golang |创建包含正则表达式元字符的字符串
)
    fmt.Println(res3)

    res4 := regexp.QuoteMeta(`String 4: ^$*-,`)
    fmt.Println(res4)

}
```

**输出:**

```go
String 1: \.\+\*\(\)\|\[\]\{\}\^\$
String 2: \+\(\)\*
String 3: \[\]\|\{\}\$
String 4: \^\$\*-,

```

**例 2:**

```go
// Go program to illustrate how to create
// a string that escapes all regular
// expression metacharacters
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Creating and initializing string
    // Using shorthand declaration
    s1 := `+*?()|[]^
 Golang |创建包含正则表达式元字符的字符串

    s2 := `+*?()|[]^$
    `
    if s1 == s2 {

        // Escaping all regular
        // expression metacharacters
        // Using QuoteMeta () function
        res := regexp.QuoteMeta(s1)
        fmt.Println("String:", res)

    } else {

        fmt.Println("Not Equal")
    }

}
```

**输出:**

```go
Not Equal
```