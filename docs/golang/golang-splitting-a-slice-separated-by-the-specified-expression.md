# Golang |分割由指定表达式分开的切片

> 原文:[https://www . geesforgeks . org/golang-spliting-a-slice-由指定表达式分隔/](https://www.geeksforgeeks.org/golang-splitting-a-slice-separated-by-the-specified-expression/)

正则表达式是定义搜索模式的字符序列。Go 语言支持正则表达式。正则表达式用于解析、过滤、验证和从大文本中提取有意义的信息，如日志、其他程序生成的输出等。
在 Go regexp 中，您可以借助 **Split()** 方法将一个切片拆分为由指定表达式分隔的子字符串。此方法返回这些表达式匹配之间的子字符串片段，计数表示要返回的子字符串数量。这个方法是在 regexp 包下定义的，所以要访问这个方法，需要在程序中导入 regexp 包。

**语法:**

```go
func (re *Regexp) Split(str string, m int) []string
```

这里如果 **m > 0** ，那么最多返回 m 个子串，最后一个字符串子串不会拆分。如果 **m == 0** ，则返回零。如果 **m < 0** ，那么它将返回所有子串。

**例 1:**

```go
// Go program to illustrate how to split a
// slice separated by the specified expression
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Splitting the given slice which is
    // separated by the given expression
    // Using Split() method
    m1 := regexp.MustCompile(`e`)

    fmt.Println(m1.Split("GeeksforGeeks", -1))
    fmt.Println(m1.Split("GeeksforGeeks", 1))
    fmt.Println(m1.Split("GeeksforGeeks", 0))
    fmt.Println(m1.Split("GeeksforGeeks", 3))
    fmt.Println(m1.Split("GeeksforGeeks", 2))
    fmt.Println()

    m2 := regexp.MustCompile(`123`)
    fmt.Println(m2.Split("123Gee123ks123Geek123s", -2))
    fmt.Println(m2.Split("123Gee123ks123Geek123s", 3))
    fmt.Println(m2.Split("123Gee123ks123Geek123s", 0))
    fmt.Println(m2.Split("123Gee123ks123Geek123s", -1))
    fmt.Println(m2.Split("123Gee123ks123Geek123s", 1))

}
```

**输出:**

```go
[G  ksforG  ks]
[GeeksforGeeks]
[]
[G  ksforGeeks]
[G eksforGeeks]

[ Gee ks Geek s]
[ Gee ks123Geek123s]
[]
[ Gee ks Geek s]
[123Gee123ks123Geek123s]

```

**例 2:**

```go
// Go program to illustrate how to split a
// slice separated by the specified expression
package main

import (
    "fmt"
    "regexp"
)

// Main function
func main() {

    // Creating and initializing a string
    // Using shorthand declaration
    s := "A vv regular vv  expression v is vv a sequence v"+
      " of vv characters v which define a vv search pattern."

    // Splitting the given slice which is
    // separated by the given expression
    // Using Split() method
    m := regexp.MustCompile(`v`)
    res1 := m.Split(s, -1)
    fmt.Println(res1)

    res2 := m.Split(s, 1)
    fmt.Println(res2)

    res3 := m.Split(s, -0)
    fmt.Println(res3)

    res4 := m.Split(s, -4)
    fmt.Println(res4)

}
```

**输出:**

```go
[A    regular     expression   is    a sequence   of    characters   which define a    search pattern.]
[A vv regular vv  expression v is vv a sequence v of vv characters v which define a vv search pattern.]
[]
[A    regular     expression   is    a sequence   of    characters   which define a    search pattern.]

```