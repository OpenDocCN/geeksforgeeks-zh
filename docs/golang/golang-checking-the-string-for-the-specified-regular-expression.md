# Golang |检查指定正则表达式的字符串

> 原文:[https://www . geesforgeks . org/golang-检查指定正则表达式的字符串/](https://www.geeksforgeeks.org/golang-checking-the-string-for-the-specified-regular-expression/)

正则表达式是定义搜索模式的字符序列。Go 语言支持正则表达式。正则表达式用于解析、过滤、验证和从大文本中提取有意义的信息，如日志、其他程序生成的输出等。
在 Go regexp 中，允许您借助 **MatchString()** 函数检查给定的字符串是否包含指定正则表达式模式的任何匹配。这个函数是在 regexp 包下定义的，所以要访问这个方法，你需要在程序中导入 regexp 包。

**语法:**

```go
func MatchString(pattern string, s string) (matched bool, err error)
```

这里 **p** 代表图案， **str** 代表一根弦。如果图案匹配，该功能返回*真*，如果图案不匹配，则返回*假*。并且如果发现也返回一个错误。

**示例:**

```go
// Go program to illustrate how to check the 
// given regexp present in the given string
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Creating and initializing string
    // Using shorthand declaration
    s1 := "Welcome to GeeksforGeeks"
    s2 := "I like Go language!!!"

    // Pattern
    p1 := "to"
    p2 := "ang"
    p3 := "OO"
    p4 := "!"

    // Matching pattern
    // Using MatchString() function
    res1, e := regexp.MatchString(p1, s1)
    fmt.Println("Result and Error is:", res1, e)

    res2, e := regexp.MatchString(p2, s1)
    fmt.Println("Result and Error is:", res2, e)

    res3, e := regexp.MatchString(p3, s1)
    fmt.Println("Result and Error is:", res3, e)

    res4, e := regexp.MatchString(p4, s1)
    fmt.Println("Result and Error is:", res4, e)

    res5, e := regexp.MatchString(p1, s2)
    fmt.Println("Result and Error is:", res5, e)

    res6, e := regexp.MatchString(p2, s2)
    fmt.Println("Result and Error is:", res6, e)

    res7, e := regexp.MatchString(p3, s2)
    fmt.Println("Result and Error is:", res7, e)

    res8, e := regexp.MatchString(p4, s2)
    fmt.Println("Result and Error is:", res8, e)

}
```

**输出:**

```go
Result and Error is: true <nil>
Result and Error is: false <nil>
Result and Error is: false <nil>
Result and Error is: false <nil>
Result and Error is: false <nil>
Result and Error is: true <nil>
Result and Error is: false <nil>
Result and Error is: true <nil>

```

**示例:**

```go
// Go program to illustrate how to check
// the given regexp present in the string
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Matching pattern in the 
    // given string using
    // MatchString() function
    res1, e := regexp.MatchString(`eks`, "GeeksforGeeks")
    fmt.Println(res1, e)

    res2, e := regexp.MatchString(`BAN`, "Banana")
    fmt.Println(res2, e)

    res3, e := regexp.MatchString(`123`, "Welcome to GeeksforGeeks")
    fmt.Println(res3, e)

    res4, e := regexp.MatchString(`e(ks`, "GFG")
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