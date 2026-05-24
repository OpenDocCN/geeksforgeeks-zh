# Golang 中的字符串.LastIndexByte()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-lastindexbyte-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-lastindexbyte-function-in-golang-with-examples/)

Golang 中的**string s.LastIndexByte()函数**返回原始字符串中给定字节的最后一个实例的索引。 如果给定的字节在原始字符串中不可用，则此方法将返回-1。

**语法：**

```go
func LastIndexByte(str string, b byte) int

```

这里，str 是原始字符串，b 是一个字节，我们要查找其最后一个索引值。

**返回值：**返回整数。

**示例 1：**

```go
// Golang program to illustrate the
// strings.LastIndexByte() Function
package main

// importing fmt and strings
import (
    "fmt"
    "strings"
)

// calling main method
func main() {

    // returns the last index of 'g' in string.
    fmt.Println(strings.LastIndexByte("geeksforgeeks", 'g'))

    // returns the last index of 'k' in string.
    fmt.Println(strings.LastIndexByte("geekgeekgeek", 'k'))
}
```

发帖主题：Re：Колибри0.7.0

```go
8
11

```

**示例 2：**

```go
// Golang program to illustrate the
// strings.LastIndexByte() Function
package main

// importing fmt and strings
import (
    "fmt"
    "strings"
)

// calling main method
func main() {

    // performs case-insensitive search(returns -1).
    fmt.Println(strings.LastIndexByte("GeeksForGeeks", 'g'))

    // performs case-insensitive search(returns -1).
    fmt.Println(strings.LastIndexByte("GeeKGeeKGeeK", 'k'))
}
```

发帖主题：Re：Колибри0.7.0

```go
-1
-1

```