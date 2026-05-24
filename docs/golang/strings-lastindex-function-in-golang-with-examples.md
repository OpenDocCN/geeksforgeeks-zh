# Golang 中的 string s.LastIndex()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-lastindex-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-lastindex-function-in-golang-with-examples/)

Golang 中的函数返回子字符串的最后一个实例在给定字符串中出现的起始索引。 如果没有找到子字符串，则返回-1。 因此，此函数返回整数值。 以零作为字符串的起始索引来计算索引。

**语法：**

```go
func LastIndex(str, substring string) int
```

这里，str 是原始字符串，substring 是我们要查找其最后索引值的字符串。

**示例 1：**

```go
// Golang program to illustrate the
// strings.LastIndex() Function
package main

import (
    "fmt"
    "strings"
)

func main() {

    // taking a string
    str := "GeeksforGeeks"
    substr := "Geeks"
    fmt.Println(strings.LastIndex(str, substr))

}
```

发帖主题：Re：Колибри0.7.0

```go
8
```

字符串为“GeeksforGeek”，子字符串为“Geek”，因此编译器查找原始字符串中存在的子字符串，并显示子字符串的最后一个实例的起始索引，即 8。

**示例 2：**

```go
// Golang program to illustrate the
// strings.LastIndex() Function
package main

import (
    "fmt"
    "strings"
)

func main() {

    // taking strings
    str := "My favorite sport is football"
    substr1 := "f"
    substr2 := "ll"
    substr3 := "SPORT"

    // using the function
    fmt.Println(strings.LastIndex(str, substr1))
    fmt.Println(strings.LastIndex(str, substr2))
    fmt.Println(strings.LastIndex(str, substr3))
}
```

发帖主题：Re：Колибри0.7.8.0

字符串是“我最喜欢的运动是足球”，子字符串是“f”、“ll”和“SPORT”，因此编译器在前两种情况下分别将输出显示为 21 和 27，并且由于第三个子字符串是“SPORT”，它被认为不存在于字符串中，因为函数区分大小写，所以它将结果显示为-1。