# Golang 中的 string.EqualFold()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-equalfold-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-equalfold-function-in-golang-with-examples/)

**Golang 中的 EqualFold()函数**报告在 Unicode 大小写折叠下 s 和 t(解释为 UTF-8 字符串)是否相等，这是不区分大小写的更一般形式。

**语法：**

```go
func EqualFold(s1, s2 string) bool

```

这里，S1 和 S2 是字符串。

**返回值：**返回布尔值。

**示例 1：**

```go
// Golang program to illustrate the
// strings.EqualFold() Function
package main

// importing fmt and strings
import (
    "fmt"
    "strings"
)

// calling main method
func main() {
    // case insensitive comparing and returns true.
    fmt.Println(strings.EqualFold("Geeks", "Geeks"))

    // case insensitive comparing and returns true.
    fmt.Println(strings.EqualFold("computerscience", "computerscience"))
}
```

发帖主题：Re：Колибри0.7.0

```go
true
true

```

**示例 2：**

```go
// Golang program to illustrate the
// strings.EqualFold() Function
package main

// importing fmt and strings
import (
    "fmt"
    "strings"
)

// calling main method
func main() {

    // case insensitive comparing and returns true.
    fmt.Println(strings.EqualFold("Geeks", "geeks"))

    // case insensitive comparing and returns true.
    fmt.Println(strings.EqualFold("COMPUTERSCIENCE", "computerscience"))
}
```

发帖主题：Re：Колибри0.7.0

```go
true

```