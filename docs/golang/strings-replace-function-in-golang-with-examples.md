# Golang 中的 string。Replace()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-replace-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-replace-function-in-golang-with-examples/)

Golang 中的**string s.Replace()函数用于返回给定字符串的副本，其中前 n 个不重叠的旧实例被新实例替换。**

**语法：**

```go
func Replace(s, old, new string, n int) string
```

这里，s 是原始或给定的字符串，old 是要替换的字符串。 New 是替换旧的，n 是替换*个旧的*的次数。

**注意：**如果 old 为空，则在字符串开头和每个 UTF-8 序列之后匹配，从而为 k 符文字符串生成最多 k+1 个替换。 如果 n<0，则对替换次数没有限制。

**示例 1：**

```go
// Golang program to illustrate the usage of
// strings.Replace() function

package main

import (
    "fmt"
    "strings"
)

func main() {
    // using the function
    fmt.Println(strings.Replace("gfg gfg gfg", "g", "G", 3))
    fmt.Println(strings.Replace("gfg gfg gfg", "fg", "FG", -1))
}
```

发帖主题：Re：Колибри0.7.8.0

在第一种情况下，“GFG”中“g”的前 3 个匹配的子字符串被替换为“G”。 在第二种情况下，每个匹配的“fg”大小写都会被“fg”替换。

**示例 2：**让我们考虑一个示例，其中我们没有为*old*传递任何值。

```go
// Golang program to illustrate the usage of
// strings.Replace() function

package main

import (
    "fmt"
    "strings"
)

func main() {

    // using the function
    fmt.Println(strings.Replace("i am geeks", "", "G", 5))
    fmt.Println(strings.Replace("i love the geekiness", "", "F", -1))
}
```

发帖主题：Re：Колибри0.7.8.0

可以看出，每个交替位置被**新的**、**n**次替换。