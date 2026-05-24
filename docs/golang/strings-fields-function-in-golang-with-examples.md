# Golang 中的 string s.Fields()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-fields-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-fields-function-in-golang-with-examples/)

Golang 中的函数用于围绕*unicode.IsSpace*定义的一个或多个连续空格字符的每个实例拆分给定的字符串，如果 str 只包含空格，则返回 str 的子字符串片段或空片段。

> **语法：**
> 
> ```go
> func Fields(str string) []string
> ```
> 
> **返回：**字符串的子字符串切片，如果字符串只包含空格，则返回空切片。

**示例 1：**

```go
// Golang program to illustrate the
// strings.Fields() Function
package main

import (
    "fmt"
    "strings"
)

func main() {   

    // String s is split on the basis of white spaces
    // and store in a string array
    s := "GeeksforGeeks is a computer science portal !"
    v := strings.Fields(s)
    fmt.Println(v)     

    // Another example by passing the string as argument
    // directly to the Fields() function
    v = strings.Fields("I am a software developer, I love coding")
    fmt.Println(v)
}
```

发帖主题：Re：Колибри0.7.0

```go
[GeeksforGeeks is a computer science portal !]
[I am a software developer, I love coding]

```

**示例 2：**

```go
// Golang program to illustrate the
// strings.Fields() Function
package main

import (
    "fmt"
    "strings"
)

func main() {

    // Fields function also splits the string
    // on the basis of white spaces and tabs
    s := strings.Fields(" I \t love \n to \n code \n all \t day.")
    fmt.Println(s)

    // Splits into 5 words which have
    // newline character in between
    s = strings.Fields("I\nam\nlearning\nGo\nlanguage")
    fmt.Println(s)
}
```

发帖主题：Re：Колибри0.7.0

```go
[I love to code all day.]
[I am learning Go language]

```