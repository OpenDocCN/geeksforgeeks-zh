# Golang 中的 strings.IndexByte()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-indexbyte-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-indexbyte-function-in-golang-with-examples/)

Golang 中的**string s.IndexByte()函数**返回原始字符串中给定字节的第一个实例的索引。 如果给定的字节在原始字符串中不可用，则此方法将返回-1。

**语法：**

```go
func IndexByte(str string, b byte) int

```

这里，str 是原始字符串，b 是一个字节，我们要查找其索引值。 让我们借助一个例子来讨论这个概念：

**示例 1：**

```go
// Golang program to illustrate the
// strings.IndexByte() Function
package main

// importing fmt and strings
import (
    "fmt"
    "strings"
)

// calling main method
func main() {

    // 'g' present at index 0 of string.
    fmt.Println(strings.IndexByte("geeksforgeeks", 'g'))

    // 's' present at index 8 of string.
    fmt.Println(strings.IndexByte("computerscience", 's'))
}
```

发帖主题：Re：Колибри0.7.0

```go
0
8

```

**示例 2：**

```go
// Golang program to illustrate the
// strings.IndexByte() Function
package main

// importing fmt and strings
import (
    "fmt"
    "strings"
)

// calling main method
func main() {

    // 's' not present in string.
    fmt.Println(strings.IndexByte("computerscience", 'S'))
    // 'f' not present in string.
    fmt.Println(strings.IndexByte("GFG", 'f'))
}
```

发帖主题：Re：Колибри0.7.0

```go
-1
-1

```