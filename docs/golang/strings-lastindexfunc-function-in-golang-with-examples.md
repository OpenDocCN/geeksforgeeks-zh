# Golang 中的 Strings.LastIndexFunc()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-lastindexfunc-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-lastindexfunc-function-in-golang-with-examples/)

Golang 中的**Strings.LastIndexFunc()函数**返回满足 func(C)的最后一个 Unicode 代码点的字符串 s 的索引，如果没有找到匹配项，则返回-1。

**语法：**

```go
func LastIndexFunc(s string, f func(rune) bool) int

```

这里，s 是字符串，func()是函数。

**返回值：**返回整数。

**示例 1：**

```go
// Golang program to illustrate the
// strings.LastIndexFunc() Function
package main

// importing fmt, strings and unicode
import (
    "fmt"
    "strings"
    "unicode"
)

// calling main method
func main() {

    // returns the last index of number.
    fmt.Println(strings.LastIndexFunc("GeeksForGeeks123", unicode.IsNumber))

    // returns the last index of number.
    fmt.Println(strings.LastIndexFunc("23Geeks1", unicode.IsNumber))
}
```

发帖主题：Re：Колибри0.7.0

```go
15
7

```

**示例 2：**

```go
// Golang program to illustrate the
// strings.LastIndexFunc() Function
package main

// importing fmt, strings and unicode
import (
    "fmt"
    "strings"
    "unicode"
)

// calling main method
func main() {

    // returns the last index of letter.
    fmt.Println(strings.LastIndexFunc("GeeksForGeeks123", unicode.IsLetter))

    // returns the last index of letter.
    fmt.Println(strings.LastIndexFunc("23Geeks1", unicode.IsLetter))
}
```

发帖主题：Re：Колибри0.7.0

```go
12
6

```