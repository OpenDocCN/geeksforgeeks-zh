# Golang 中的 strings.IndexRune()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-indexrune-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-indexrune-function-in-golang-with-examples/)

Golang 中的函数用于查找给定字符串中指定符文的第一个索引。 它是在字符串包下定义的，因此必须在程序中导入字符串包才能访问 IndexRune 函数

**语法：**

```go
func IndexRune(str string, r rune) int
```

此函数返回 Unicode 代码点的第一个实例(即指定的符文)的索引，如果指定的符文不在给定字符串中，则返回-1。 如果符文是 utf8.RuneError，则它返回任何无效 UTF-8 字节序列的第一个实例。

**示例 1：**

```go
// Golang program to show the usage
// of strings.IndexRune() Function
package main

// importing fmt and strings
import (
    "fmt"
    "strings"
)

func main() {

    // Returns the index of 'G' in string.
    fmt.Println(strings.IndexRune("This is GeeksForGeeks", 'G'))

    // Returns -1 because 'y' is not present in string.
    fmt.Println(strings.IndexRune("This is GeeksForGeeks", 'y'))
}
```

发帖主题：Re：Колибри0.7.0

```go
8
-1

```

**示例 2：**

```go
// Golang program to show the usage
// of strings.IndexRune() Function
package main

// importing fmt and strings
import (
    "fmt"
    "strings"
)

func main() {

    // Returns -1 because of case-sensitive matching.
    fmt.Println(strings.IndexRune("This is GeeksForGeeks", 'g'))

    // Returns the index of space in string.
    fmt.Println(strings.IndexRune("This is GeeksForGeeks", ' '))
}
```

发帖主题：Re：Колибри0.7.0

```go
-1
4

```