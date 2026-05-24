# Golang 中的 strings.Join()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-join-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-join-function-in-golang-with-examples/)

Golang 中的**strs.Join()函数**将字符串片段中的所有元素连接成一个字符串。 此函数在字符串包中提供。

**语法：**

```go
func Join(s []string, sep string) string

```

这里，*s*是我们可以用来连接元素的字符串，而 sep 是放置在最终字符串中元素之间的分隔符。

**返回值：**它返回一个字符串。

**示例 1：**

```go
// Golang program to illustrate the
// use of strings.Join Function

package main

// importing fmt and strings
import (
    "fmt"
    "strings"
)

// calling main method
func main() {

    // array of strings.
    str := []string{"Geeks", "For", "Geeks"}

    // joining the string by separator
    fmt.Println(strings.Join(str, "-"))
}
```

发帖主题：Re：Колибри0.7.0

```go
Geeks-For-Geeks

```

**示例 2：**

```go
// Golang program to illustrate the
// use of strings.Join Function

package main

// importing fmt and strings
import (
    "fmt"
    "strings"
)

// calling main method
func main() {
    // array of strings.
    str := []string{"A", "Computer-science", "portal", "for", "Geeks"}
    // joining the string by separator in middle.
    fmt.Println(strings.Join(str, " "))
}
```

发帖主题：Re：Колибри0.7.0

```go
A Computer-science portal for Geeks

```