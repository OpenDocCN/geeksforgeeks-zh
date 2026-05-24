# Golang 中的 string s.NewReplacer()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-newreplacer-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-newreplacer-function-in-golang-with-examples/)

Golang 中的**string s.NewReplacer()函数**从以前的新字符串集列表中返回一个新的 Replacer。 替换是按照它们在目标字符串中显示的顺序执行的，没有重叠匹配。 旧字符串比较是按参数顺序进行的。 旧字符串比较是按参数顺序进行的。

**语法**

```go
func NewReplacer(oldnew ...string) *Replacer
```

请记住，如果提供奇数个参数，NewReplacer 会死机。

**示例 1：**

```go
// Golang program to illustrate the
// strings.NewReplacer() Function
package main

import (
    "fmt"
    "strings"
)

func main() {
    r := strings.NewReplacer("<", "<", ">", ">")
    fmt.Println(r.Replace("Hey I am <b>GFG</b>!"))
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the
// strings.NewReplacer() Function
package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {

    // using the function
    r := strings.NewReplacer("(", "easy", ")", "tough;")
    fmt.Println(r.Replace("The dsa course of geeksforgeeks is ( not )"))
}
```

发帖主题：Re：Колибри0.7.8.0