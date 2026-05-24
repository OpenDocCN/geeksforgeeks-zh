# Golang 中的 strings.Title()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-title-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-title-function-in-golang-with-examples/)

**strss.Title()函数**返回字符串 s 的副本，其中字符串的所有 Unicode 字母的开头单词都映射到其 Unicode 标题大小写。 此方法属于字符串包。

> **语法：**
> 
> ```go
> func Title(s string) string
> 
> ```
> 
> 它返回字符串。

**示例 1：**

```go
// Golang program to illustrate the strings.Title() function

package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {
    fmt.Println(strings.Title("geeks for geeks"))
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the strings.Title() function

package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {
    fmt.Println(strings.Title("computer science portal"))
}
```

发帖主题：Re：Колибри0.7.8.0