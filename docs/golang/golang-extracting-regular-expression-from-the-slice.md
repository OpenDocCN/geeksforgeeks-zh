# Golang |从切片中提取正则表达式

> 原文:[https://www . geeksforgeeks . org/golang-从切片中提取正则表达式/](https://www.geeksforgeeks.org/golang-extracting-regular-expression-from-the-slice/)

正则表达式是定义搜索模式的字符序列。Go 语言支持正则表达式。正则表达式用于解析、过滤、验证和从大文本中提取有意义的信息，如日志、其他程序生成的输出等。
在 Go regexp 中，允许借助 **Find()** 方法在给定字符串中查找正则表达式。此方法返回一个片段，该片段包含正则表达式原始片段中最左边匹配的文本。如果没有找到匹配项，则返回零。这个方法是在 regexp 包下定义的，所以要访问这个方法，需要在程序中导入 regexp 包。

**语法:**

```go
func (re *Regexp) Find(s []byte) []byte
```

**例 1:**

```go
// Go program to illustrate how to
// find regexp from the given slice
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Finding regexp from the
    // given slice of bytes
    // Using  Find() method
    m := regexp.MustCompile(`geeks?`)

    fmt.Printf("%q\n", m.Find([]byte(`GeeksgeeksGeeks, geeks`)))
    fmt.Printf("%q\n", m.Find([]byte(`Hello! geeksForGEEKs`)))
    fmt.Printf("%q\n", m.Find([]byte(`I like Go language`)))
    fmt.Printf("%q\n", m.Find([]byte(`Hello, Welcome`)))

}
```

**输出:**

```go
"geeks"
"geeks"
""
""

```

**例 2:**

```go
// Go program to illustrate how to
// find regexp from the given slice
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Finding regexp from 
    // the given slice
    // Using Find() method
    m := regexp.MustCompile(`language`)
    res := m.Find([]byte(`I like Go language this language is "+
                          "very easy to learn and understand`))

    if res == nil {

        fmt.Printf("Found: %q ", res)
    } else {
        fmt.Printf("Found: %q", res)
    }
}
```

**输出:**

```go
Found: "language"
```