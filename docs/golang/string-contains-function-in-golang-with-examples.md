# 字符串。包含 Golang 中的函数和示例

> Original: [https://www.geeksforgeeks.org/string-contains-function-in-golang-with-examples/](https://www.geeksforgeeks.org/string-contains-function-in-golang-with-examples/)

**字符串。Golang 中的函数**用于检查给定字符串中是否存在给定的字母。 如果字母出现在给定的字符串中，则返回 TRUE，否则返回 FALSE。

**语法：**

```go
func Contains(str, substr string) bool

```

这里，str 是原始字符串，substr 是要检查的字符串。 让我们借助一个例子来讨论这个概念：

**示例 1：**

```go
// Golang program to illustrate
// the strings.Contains() Function
package main

import (
    "fmt"
    "strings"
)

func main() {

    // using the function
    fmt.Println(strings.Contains("GeeksforGeeks", "for"))
    fmt.Println(strings.Contains("A computer science portal", "science"))

}
```

发帖主题：Re：Колибри0.7.0

```go
true
true

```

**解释：**在上面的示例中，我们检查不同字符串中是否存在子串‘for’和‘Science’。 由于 string s.Containes()函数返回布尔值，因此在这两种情况下都返回 TRUE。

**示例 2：**下面的示例说明了用户如何打印所需的结果，而不是布尔输出：

```go
// Golang program to illustrate
// the strings.Contains() Function
package main

import (
    "fmt"
    "strings"
)

func main() {
    input := "Golang"

    str := "This is a Golang program"

    if strings.Contains(str, input) {
        fmt.Println("Yes")
    }
}
```

发帖主题：Re：Колибри0.7.8.0

**解释：**在上面的示例中，我们将子字符串作为‘input’，将主字符串作为‘str’。 然后，我们检查主字符串中是否存在‘Golang’。 如果是，则返回‘Yes’作为输出，如上所示。