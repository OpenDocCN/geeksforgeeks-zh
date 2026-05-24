# Golang 中的 string s.Map()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-map-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-map-function-in-golang-with-examples/)

Golang 中的函数用于返回给定字符串的副本，该字符串的所有字符都根据映射函数进行了修改。 如果映射返回负值，则从字符串中删除该字符，不进行替换。

因此，每当用户想要对某个字符串进行更改时，他都可以使用 string s.Map()函数。 它用用户需要的字符替换字符串的字符。 如果我们需要屏蔽某些字符，包括数字和空格，可以使用此函数。

**语法：**

```go
func Map(mapping func(rune) rune, s string) string
```

映射函数(符文)rune 参数定义需要用来替换原始字符的字符，而 s 参数定义用户输入的原始字符串。

**示例 1：**

```go
// Golang program to illustrate 
// the strings.Map() Function
package main

import (
    "fmt";
    "strings"
)

func main() {
    modified := func(r rune) rune {
        if r == 'e' {
            return '@'
        }
        return r
    }

    input := "Hello, Welcome to GeeksforGeeks"
    fmt.Println(input)

    // using the function
    result := strings.Map(modified, input)
    fmt.Println(result)
}
```

发帖主题：Re：Колибри0.7.8.0

**解释：**在上面的示例中，我们使用了 string s.Map()函数来修改字符串。 我们定义了一个名为“Modified”的变量，它将字符串中的字符“e”替换为符号“@”。 另一个名为“input”的变量接受需要转换的输入字符串。

**示例 2：**函数的作用是：删除字符串中单词之间的空格。

```go
// Golang program to illustrate 
// the strings.Map() Function
package main

import (
    "fmt";
    "strings"
)

func main() {
    transformed := func(r rune) rune {

        if r == ' ' {
            return 0
        }
        return r
    }

    input := "GeeksforGeeks is a computer science portal."
    fmt.Println(input)

    // using the function
    output := strings.Map(transformed, input)
    fmt.Println(output)
}
```

发帖主题：Re：Колибри0.7.8.0

**解释：**在上面的示例中，我们使用 string s.Map()函数删除字符串之间的空格。 我们定义了一个名为“Transform”的变量，它消除了字符串中的空格‘’。 这是通过在空格位置返回 0 来实现的。 另一个名为“input”的变量接受需要删除中间空格的输入字符串。