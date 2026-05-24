# Golang 中的 Strings.ToValidUTF8()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-tovalidutf8-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-tovalidutf8-function-in-golang-with-examples/)

**Golang 中的 Strings.ToValidUTF8()函数**用于返回字符串 s 的副本，每次无效的 UTF-8 字节序列被替换为替换字符串(可能为空)。

**语法：**

```go
func ToValidUTF8(str, rep string) string

```

这里，str 是可能包含无效 UTF-8 的字符串，rep 是替换字符串。

**返回值：**返回替换后的字符串。

**示例 1：**

```go
// Golang program to show the usage
// of strings.ToValidUTF8() Function
package main

// importing fmt and strings
import (
    "fmt"
    "strings"
)

// calling main method
func main() {

    // There is no invalid UTF-8 character
    // present, so the same string returned
    fmt.Print(strings.ToValidUTF8("This is GeeksForGeeks", " "))
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to show the usage
// of strings.ToValidUTF8() Function
package main

// importing fmt and strings
import (
    "fmt"
    "strings"
)

// calling main method
func main() {

    // Invalid UTF-8 '\xc5' replaced by 'For'
    fmt.Print(strings.ToValidUTF8("Geeks\xc5Geeks", "For"))
}
```

发帖主题：Re：Колибри0.7.8.0