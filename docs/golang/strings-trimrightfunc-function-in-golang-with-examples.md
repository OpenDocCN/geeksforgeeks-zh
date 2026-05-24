# Golang 中的 Strings.TrimRightFunc()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-trimrightfunc-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-trimrightfunc-function-in-golang-with-examples/)

**string。TrimRightFunc()函数**返回字符串 s 的片段，其中删除了满足 f(C)的所有尾随 Unicode 代码点 c。

**语法：**

```go
func TrimRightFunc(s string, f func(rune) bool) string

```

这里，s 是字符串，func()是满足字符串字符的方法。

**返回值：**从字符串中去掉尾随字符后返回字符串。

**示例 1：**

```go
// Golang program to illustrate
// the strings.TrimRightFunc() Function
package main

// importing fmt, unicode and strings
import (
    "fmt"
    "strings"
    "unicode"
)

// Calling Main method
func main() {

    // Here we have a string. The function
    // returns true for the letters
    // and all other will trim out
    // from the string only from Right
    fmt.Print(strings.TrimRightFunc("77GeeksForGeeks!!!", func(r rune) bool {
        return !unicode.IsLetter(r)
    }))
}
```

发帖主题：Re：Колибри0.7.0

```go
77GeeksForGeeks

```

**示例 2：**

```go
// Golang program to illustrate
// the strings.TrimRightFunc() Function
package main

// importing fmt, unicode and strings
import (
    "fmt"
    "strings"
    "unicode"
)

// Calling Main method
func main() {

    // Here we have a string. The function
    // returns true for the letters
    // and numbers as well
    // and all other will trim out
    // from the string only from left
    fmt.Print(strings.TrimRightFunc("!!!34GeeksForGeeks!!!!", func(r rune) bool {
        return !unicode.IsLetter(r) && !unicode.IsNumber(r)
    }))
}
```

发帖主题：Re：Колибри0.7.0

```go
!!!34GeeksForGeeks

```