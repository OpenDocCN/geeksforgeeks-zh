# Golang |替换所有与正则表达式匹配的字符串

> 原文:[https://www . geesforgeks . org/golang-用正则表达式替换所有匹配的字符串/](https://www.geeksforgeeks.org/golang-replacing-all-string-which-matches-with-regular-expression/)

正则表达式是定义搜索模式的字符序列。Go 语言支持正则表达式。正则表达式用于解析、过滤、验证和从大文本中提取有意义的信息，如日志、其他程序生成的输出等。
在 Go regexp 中，通过 **ReplaceAllString()** 方法，如果指定的字符串与指定的正则表达式匹配，则允许用另一个字符串替换原始字符串。在此方法中， **$** 符号表示像 **$1** 一样被解释为展开，表示第一个子匹配的文本。这个方法是在 regexp 包下定义的，所以要访问这个方法，需要在程序中导入 regexp 包。

**语法:**

```go
func (re *Regexp) ReplaceAllString(str, r string) string
```

**例 1:**

```go
// Go program to illustrate how to
// replace string with the specified regexp
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Replace string with the specified regexp
    // Using ReplaceAllString() method
    m1 := regexp.MustCompile(`x(p*)y`)

    fmt.Println(m1.ReplaceAllString("xy--xpppyxxppxy-", "B"))
    fmt.Println(m1.ReplaceAllString("xy--xpppyxxppxy--", "$1"))
    fmt.Println(m1.ReplaceAllString("xy--xpppyxxppxy-", "$1P"))
    fmt.Println(m1.ReplaceAllString("xy--xpppyxxppxy-", "${1}Q"))

}
```

**输出:**

```go
B--BxxppB-
--pppxxpp--
--xxpp-
Q--pppQxxppQ-

```

**例 2:**

```go
// Go program to illustrate how to replace
// string with the specified regexp
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Creating and initializing a string
    // Using shorthand declaration
    s := "Geeks-for-Geeks-for-Geeks-for-Geeks-gfg"

    // Replacing all the strings
    // Using ReplaceAllString() method
    m := regexp.MustCompile("^(.*?)Geeks(.*){content}quot;)
    Str := "${1}GEEKS$2"
    res := m.ReplaceAllString(s, Str)
    fmt.Println(res)

}
```

**输出:**

```go
GEEKS-for-Geeks-for-Geeks-for-Geeks-gfg
```