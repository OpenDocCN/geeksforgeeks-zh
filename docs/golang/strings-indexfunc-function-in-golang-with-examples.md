# Golang 中的 strings.IndexFunc()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-indexfunc-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-indexfunc-function-in-golang-with-examples/)

Golang 中的函数用于将索引返回到满足 f(C)的第一个 Unicode 代码点的 s 中，如果没有满足 f(C)的，则返回-1。

**语法：**

```go
func IndexFunc(str string, f func(rune) bool) int

```

这里，str 是可能包含 Unicode 代码点的字符串，f 是验证 Unicode 点的函数。

**返回值：**返回满足函数的第一个 Unicode 码点的索引。

**示例 1：**

```go
// Golang program to show the usage
// of strings.IndexFunc() Function
package main

// importing fmt, unicode and strings
import (
    "fmt"
    "strings"
    "unicode"
)

func main() {

    // func f which validates the Greek 
    // Unicode character in the string
    f := func(c rune) bool {
        return unicode.Is(unicode.Greek, c)
    }

    // using the function
    fmt.Println(strings.IndexFunc("Hello Geeks!α", f)) 
}

```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to show the usage
// of strings.IndexFunc() Function
package main

// importing fmt, unicode and strings
import (
    "fmt"
    "strings"
    "unicode"
)

func main() {

    // func f which validates the Greek 
    // Unicode character in the string
    f := func(c rune) bool {
        return unicode.Is(unicode.Greek, c)
    }

    // using the function
    fmt.Println(strings.IndexFunc("GeeksforGeeks", f)) 
}
```

发帖主题：Re：Колибри0.7.8.0