# Golang |检查指定正则表达式的切片字节

> 原文:[https://www . geeksforgeeks . org/golang-检查指定正则表达式的片字节数/](https://www.geeksforgeeks.org/golang-checking-the-byte-of-slice-for-specified-regular-expression/)

正则表达式是定义搜索模式的字符序列。Go 语言支持正则表达式。正则表达式用于解析、过滤、验证和从大文本中提取有意义的信息，如日志、其他程序生成的输出等。
在 Go regexp 中，允许您借助 **Match()** 函数检查给定的切片字节是否包含指定正则表达式模式的任何匹配。这个函数是在 regexp 包下定义的，所以要访问这个方法，你需要在程序中导入 regexp 包。

**语法:**

```go
func Match(p string, s []byte) (result bool, err error)
```

这里，p 代表模式，s 代表字节片。如果模式匹配，此函数返回 true 如果模式不匹配，则返回 false。并且如果发现也返回一个错误。

**例 1:**

```go
// Go program to illustrate how to check
// the given regexp present in the given slice
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Creating and initializing
    // slice of bytes
    // Using shorthand declaration
    s1 := []byte{'G', 'E', 'E', 'K', 'S', 'F', 'O',
                      'R', 'G', 'E', 'E', 'K', 'S'}

    s2 := []byte{'g', 'f', 'g'}

    // Pattern
    p1 := "G"
    p2 := "g"
    p3 := "^^"
    p4 := "@"

    // Matching pattern
    // Using Match() function
    res1, e := regexp.Match(p1, s1)
    fmt.Println("Result and Error is:", res1, e)

    res2, e := regexp.Match(p2, s1)
    fmt.Println("Result and Error is:", res2, e)

    res3, e := regexp.Match(p3, s1)
    fmt.Println("Result and Error is:", res3, e)

    res4, e := regexp.Match(p4, s1)
    fmt.Println("Result and Error is:", res4, e)

    res5, e := regexp.Match(p1, s2)
    fmt.Println("Result and Error is:", res5, e)

    res6, e := regexp.Match(p2, s2)
    fmt.Println("Result and Error is:", res6, e)

    res7, e := regexp.Match(p3, s2)
    fmt.Println("Result and Error is:", res7, e)

    res8, e := regexp.Match(p4, s2)
    fmt.Println("Result and Error is:", res8, e)

}
```

**输出:**

```go
Result and Error is: true <nil>
Result and Error is: false <nil>
Result and Error is: true <nil>
Result and Error is: false <nil>
Result and Error is: false <nil>
Result and Error is: true <nil>
Result and Error is: true <nil>
Result and Error is: false <nil>

```

**例 2:**

```go
// Go program to illustrate how to check
// the given regexp present in the given slice
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Matching pattern in the
    // given slice of bytes
    // Using Match() function
    res1, e := regexp.Match(`eks`, []byte(`GeeksforGeeks`))
    fmt.Println(res1, e)

    res2, e := regexp.Match(`BAN`, []byte(`Banana`))
    fmt.Println(res2, e)

    res3, e := regexp.Match(`123`, []byte(`GeeksforGeeks`))
    fmt.Println(res3, e)

    res4, e := regexp.Match(`e(ks`, []byte(`GeeksforGeeks`))
    fmt.Println(res4, e)

}
```

**输出:**

```go
true <nil>
false <nil>
false <nil>
false error parsing regexp: missing closing ): `e(ks`

```