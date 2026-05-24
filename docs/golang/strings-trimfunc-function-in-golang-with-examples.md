# Golang 中的 strings.TrimFunc()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-trimfunc-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-trimfunc-function-in-golang-with-examples/)

Golang 中的函数用于返回字符串 s 的片段，其中删除了满足 f(C)的所有前导和尾随 Unicode 代码点 c。

**语法：**

```go
func TrimFunc(s string, f func(rune) bool) string

```

这里，s 是字符串，函数检查 rune 的值，如果可以修剪，则返回 true。

**返回类型：**从字符串中删除指定字符后返回字符串。

**示例 1：**

```go
// Golang program to illustrate
// the strings.TrimFunc() Function
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
    // from the string
    fmt.Print(strings.TrimFunc("77GeeksForGeeks!!!", func(r rune) bool {
        return !unicode.IsLetter(r)
    }))
}
```

发帖主题：Re：Колибри0.7.0

```go
GeeksForGeeks

```

**示例 2：**

```go
// Golang program to illustrate
// the strings.TrimFunc() Function

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
    // from the string
    fmt.Print(strings.TrimFunc("1234GeeksForGeeks!!!!", func(r rune) bool {
        return !unicode.IsLetter(r) && !unicode.IsNumber(r)
    }))
}
```

发帖主题：Re：Колибри0.7.0

```go
1234GeeksForGeeks

```