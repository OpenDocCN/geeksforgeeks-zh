# Golang |从字符串中提取正则表达式

> 原文:[https://www . geesforgeks . org/golang-从字符串中提取正则表达式/](https://www.geeksforgeeks.org/golang-extracting-a-regular-expression-from-the-string/)

正则表达式是定义搜索模式的字符序列。Go 语言支持正则表达式。正则表达式用于解析、过滤、验证和从大文本中提取有意义的信息，如日志、其他程序生成的输出等。
在 Go regexp 中，您可以借助 **FindString()** 方法从给定的字符串中提取正则表达式。此方法返回一个字符串，该字符串包含正则表达式给定字符串中最左边匹配的文本。如果没有找到匹配项，那么这个方法将返回一个空字符串，但是如果正则表达式成功地匹配了一个空字符串，它也将返回一个空字符串。这个方法是在 regexp 包下定义的，所以要访问这个方法，需要在程序中导入 regexp 包。

**语法:**

```go
func (re *Regexp) FindString(str string) string
```

**例 1:**

```go
// Go program to illustrate how to find
// the regexp from the given string

package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Finding regexp from the given string
    // Using FindString() method
    m := regexp.MustCompile(`geek`)

    fmt.Println(m.FindString("GeeksgeeksGeeks, geeks"))
    fmt.Println(m.FindString("Hello! geeksForGEEKs"))
    fmt.Println(m.FindString("I like Go language"))
    fmt.Println(m.FindString("Hello, Welcome"))

}
```

**输出:**

```go
geek
geek

```

**例 2:**

```go
// Go program to illustrate how to find
// the regexp from the given string
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Finding the regexp from the given string
    // Using Find() method
    m := regexp.MustCompile(`like.?`)
    res := m.FindString("I45, like345, Go-234 langu34age")

    // Finding the index value of 
    // regexp in the given string
    // UsingFindStringIndex() method
    r := m.FindStringIndex("I45, like345, Go-234 langu34age")

    fmt.Printf("Found: %s with index value: %d", res, r)
}
```

**输出:**

```go
Found: like3 with index value: [5 10]
```