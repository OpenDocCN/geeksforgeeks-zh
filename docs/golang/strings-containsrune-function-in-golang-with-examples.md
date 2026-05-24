# Golang 中的 string s.ContainsRune()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-containsrune-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-containsrune-function-in-golang-with-examples/)

Unicode 是 ASCII 的超集，包含世界上所有书写系统中的字符，是目前正在使用的字符集。 Unicode 系统中的每个字符都由 Unicode 代码点唯一标识，在 Golang 中称为**符文**。 要了解更多有关符文的信息，请阅读文章[Runes in Golang](https://www.geeksforgeeks.org/rune-in-golang/)
**字符串。Golang 中的 ContainsRune()函数**用于检查给定的字符串是否包含指定的符文。

> **语法：**
> 
> ```go
> func ContainsRune(s string, r rune) bool
> ```
> 
> 这里，str 是字符串，r 是 s rune。
> 
> 如果符文指定的字符出现在字符串中，则返回布尔值 TRUE，否则返回 FALSE。

**示例 1：**

```go
// Golang program to illustrate the
// strings.ContainsRune() Function
package main

import (
    "fmt"
    "strings"
)

func main() {

    // using the function
    fmt.Println(strings.ContainsRune("geeksforgeeks", 97))
}
```

发帖主题：Re：Колибри0.7.0

```go
false

```

以上代码返回 FALSE，因为在传递的字符串“geeksforgeek”中不存在由符文或 Unicode 代码点 97(即‘a’)指定的字符。

**示例 2：**

```go
// Golang program to illustrate the
// strings.ContainsRune() Function
package main

import (
    "fmt"
    "strings"
)

func main() {
    str := "geeksforgeeks"

    // using the function
    if strings.ContainsRune(str, 103) {
        fmt.Println("Yes")
    } else {
        fmt.Println("No")
    }
}
```

发帖主题：Re：Колибри0.7.0

```go
Yes

```