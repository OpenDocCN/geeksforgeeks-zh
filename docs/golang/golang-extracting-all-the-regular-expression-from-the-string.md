# Golang |从字符串中提取所有正则表达式

> 原文:[https://www . geesforgeks . org/golang-从字符串中提取所有正则表达式/](https://www.geeksforgeeks.org/golang-extracting-all-the-regular-expression-from-the-string/)

正则表达式是定义搜索模式的字符序列。Go 语言支持正则表达式。正则表达式用于解析、过滤、验证和从大文本中提取有意义的信息，如日志、其他程序生成的输出等。
在 Go regexp 中，可以借助**findallsstring()**方法找到给定字符串中的所有正则表达式。此方法返回指定正则表达式的所有连续匹配的片段，如包注释中的“全部”描述所定义。或者，如果没有找到匹配项，这个方法将返回零，这里 count 表示返回片段的子串数。这个方法是在 regexp 包下定义的，所以要访问这个方法，需要在程序中导入 regexp 包。

**语法:**

```go
func (re *Regexp) FindAllString(str string, m int) []string
```

**例 1:**

```go
// Go program to illustrate how to find
// all the regexp from the given slice
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Finding all regexp from 
    // the given string
    // Using FindAllString () method
    m := regexp.MustCompile(`geeks.`)

    fmt.Println(m.FindAllString("GeeksgeeksGeeks, geeks", -1))
    fmt.Println(m.FindAllString("Hello! geeksForGEEKsgeeks-geeks", 2))
    fmt.Println(m.FindAllString("I like Go language", 0))
    fmt.Println(m.FindAllString("Hello, Welcome", 1))

}
```

**输出:**

```go
[geeksG]
[geeksF geeks-]
[]
[]

```

**例 2:**

```go
// Go program to illustrate how to find
// all the regexp from the given slice
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Finding the number from 
    // the given string
    // Using FindAllStrings() method
    s := "I45, like345, Go-234 langu34age"

    m := regexp.MustCompile(`[-]?\d[\d]*[\]?[\d{2}]*`)
    res := m.FindAllString(s, 2)
    for _, ele := range res {
        fmt.Println("Number:", ele)
    }
}
```

**输出:**

```go
Number: 45
Number: 345

```