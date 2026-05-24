# Golang |查找字符串中存在的正则表达式的索引

> 原文:[https://www . geesforgeks . org/golang-find-index-of-the-正则表达式-in-present-in-string/](https://www.geeksforgeeks.org/golang-finding-index-of-the-regular-expression-present-in-string/)

正则表达式是定义搜索模式的字符序列。Go 语言支持正则表达式。正则表达式用于解析、过滤、验证和从大文本中提取有意义的信息，如日志、其他程序生成的输出等。
在 Go regexp 中，可以借助 **FindStringIndex()** 方法找到给定字符串中指定正则表达式最左边的索引值。此方法返回一个由两个元素组成的整数片，它定义了正则表达式给定字符串中最左边匹配的位置，以及类似 str[loc[0]:loc[1]]的匹配。否则，如果没有找到匹配，它将返回零。这个方法是在 regexp 包下定义的，所以要访问这个方法，需要在程序中导入 regexp 包。

**语法:**

```go
func (re *Regexp) FindStringIndex(str string) (loc []int)
```

**例 1:**

```go
// Go program to illustrate how to find the
// index value of the regexp in the given string

package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Finding index regexp 
    // from the given string
    // Using FindStringIndex() method
    m := regexp.MustCompile(`ee`)

    fmt.Println(m.FindStringIndex("GeeksgeeksGeeks, geeks"))
    fmt.Println(m.FindStringIndex("Hello! geeksForGEEKs"))
    fmt.Println(m.FindStringIndex("I like Go language"))
    fmt.Println(m.FindStringIndex("Hello, Welcome"))

}
```

**输出:**

```go
[1 3]
[8 10]
[]
[]

```

**例 2:**

```go
// Go program to illustrate how to find the index
// value of the regexp in the given string
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Finding the regexp 
    // from the given string
    // Using Find() method
    m := regexp.MustCompile(`345`)
    res := m.FindString("I45, like345, Go-234 langu34age")

    // Finding the index value of regexp in the given string
    // UsingFindStringIndex() method
    r := m.FindStringIndex("I45, like345, Go-234 langu34age")
    fmt.Printf("Found: %s with index value: %d", res, r)
}
```

**输出:**

```go
Found: 345 with index value: [9 12]
```