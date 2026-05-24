# Golang 中的 Strings.ToTitleSpecial()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-totitlespecial-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-totitlespecial-function-in-golang-with-examples/)

**Golang 中的 Strings.ToTitleSpecial()函数**用于返回字符串 s 的副本，所有 Unicode 字母都映射到其 Unicode 标题大小写，优先考虑特殊的大小写规则。

**语法：**

```go
func ToTitleSpecial(c unicode.SpecialCase, s string) string
```

这里，c 是大小写映射，s 是指定的字符串。

**示例 1：**

```go
// Golang program to illustrate
// the strings.ToTitleSpecial Function
package main

import (
    "fmt"
    "strings"
    "unicode"
)

func main() {

    // using the function
    fmt.Println(strings.ToTitleSpecial(unicode.TurkishCase, "geeks for geeks"))
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate
// the strings.ToTitleSpecial Function
package main

import (
    "fmt"
    "strings"
    "unicode"
)

func main() {

    // using the function
    fmt.Println(strings.ToTitleSpecial(unicode.TurkishCase, "I am a student"))
}
```

发帖主题：Re：Колибри0.7.8.0