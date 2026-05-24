# Golang 中的 Strings.TrimLeftFunc()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-trimleftfunc-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-trimleftfunc-function-in-golang-with-examples/)

**string。TrimLeftFunc()函数**返回字符串 s 的片段，其中删除了满足 f(C)的所有前导 Unicode 代码点 c。

**语法：**

```go
func TrimLeftFunc(s string, f func(rune) bool) string

```

这里，s 是字符串，func()是满足字符串字符的方法。

**返回值：**从字符串中去掉前导字符后返回字符串。

**示例 1：**

```go
// Golang program to illustrate
// the strings.TrimLeftFunc() Function
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
    // from the string only from Left
    fmt.Print(strings.TrimLeftFunc("77GeeksForGeeks!!!", func(r rune) bool {
        return !unicode.IsLetter(r)
    }))
}
```

发帖主题：Re：Колибри0.7.0

```go
GeeksForGeeks!!!

```

**示例 2：**

```go
// Golang program to illustrate
// the strings.TrimLeftFunc() Function
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
    fmt.Print(strings.TrimLeftFunc("!!!34GeeksForGeeks!!!!", func(r rune) bool {
        return !unicode.IsLetter(r) && !unicode.IsNumber(r)
    }))
}
```

发帖主题：Re：Колибри0.7.0

```go
34GeeksForGeeks!!!!

```