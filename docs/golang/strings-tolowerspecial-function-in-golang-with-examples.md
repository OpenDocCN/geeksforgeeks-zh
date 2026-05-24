# Golang 中的 Strings.ToLowerSpecial()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-tolowerspecial-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-tolowerspecial-function-in-golang-with-examples/)

**Golang 中的 Strings.ToLowerSpecial()函数**用于返回字符串 s 的副本，其中所有 Unicode 字母使用 c 指定的大小写映射到其小写字母。

**语法：**

```go
func ToLowerSpecial(c unicode.SpecialCase, s string) string
```

这里，c 是大小写映射，s 是指定的字符串。

**示例 1：**

```go
// Golang program to illustrate
// the strings.ToLowerSpecial Function
package main

import (
    "fmt"
    "strings"
    "unicode"
)

func main() {

    // using the function
    fmt.Println(strings.ToLowerSpecial(unicode.TurkishCase, "Hello, Geeks"))
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate
// the strings.ToLowerSpecial Function
package main

import (
    "fmt"
    "strings"
    "unicode"
)

func main() {

    // using the function
    fmt.Println(strings.ToLowerSpecial(unicode.TurkishCase, "Computer Portal"))
}
```

发帖主题：Re：Колибри0.7.8.0