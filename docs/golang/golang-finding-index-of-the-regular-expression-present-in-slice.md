# Golang |寻找切片中存在的正则表达式的索引

> 原文:[https://www . geesforgeks . org/golang-find-index-of-the-正则表达式-in-present-in-slice/](https://www.geeksforgeeks.org/golang-finding-index-of-the-regular-expression-present-in-slice/)

正则表达式是定义搜索模式的字符序列。Go 语言支持正则表达式。正则表达式用于解析、过滤、验证和从大文本中提取有意义的信息，如日志、其他程序生成的输出等。
在 Go regexp 中，可以借助 **FindIndex()** 方法，在给定的字节片内找到指定正则表达式最左边的索引值。此方法返回一个由两个元素组成的整数切片，它定义了正则表达式给定切片中最左边匹配的位置，以及像 s[loc[0]:loc[1]]这样的匹配。否则，如果没有找到匹配，它将返回零。这个方法是在 regexp 包下定义的，所以要访问这个方法，需要在程序中导入 regexp 包。

**语法:**

```go
func (re *Regexp) FindIndex(s []byte) (loc []int)
```

**例 1:**

```go
// Go program to illustrate how to find the index
// value of the regexp in the given slice

package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Finding the index value of regexp 
    // from the given slice of bytes
    // Using FindIndex() method
    m := regexp.MustCompile(`ek`)

    fmt.Println(m.FindIndex([]byte(`GeeksgeeksGeeks, geeks`)))
    fmt.Println(m.FindIndex([]byte(`Hello! geeksForGEEKs`)))
    fmt.Println(m.FindIndex([]byte(`I like Go language`)))
    fmt.Println(m.FindIndex([]byte(`Hello, Welcome`)))

}
```

**输出:**

```go
[2 4]
[9 11]
[]
[]

```

**例 2:**

```go
// Go program to illustrate how to find the
// index value of the regexp in the given slice
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Finding regexp from
    // the given slice
    // Using Find() method
    m := regexp.MustCompile(`45`)
    res := m.Find([]byte(`I45, like345, Go-234 langu34age`))

    if res == nil {
        fmt.Println("Nil found")
    } else {

        // Finding the index value of
        // the regexp from the given slice
        // Using FindIndex() method
        r := m.FindIndex([]byte(`I45, like345, Go-234 langu34age`))
        fmt.Printf("Found: %q with index value: %d", res, r)
    }
}
```

**输出:**

```go
Found: "45" with index value: [1 3]
```