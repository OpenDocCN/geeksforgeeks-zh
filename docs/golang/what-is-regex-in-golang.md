# 戈朗的 Regex 是什么？

> Original: [https://www.geeksforgeeks.org/what-is-regex-in-golang/](https://www.geeksforgeeks.org/what-is-regex-in-golang/)

正则表达式(或 RegEx)是定义用于匹配特定文本的搜索模式的特殊字符序列。 在 Golang 中，有一个用于正则表达式的内置包，称为**regexp**包，它包含过滤、替换、验证或提取等所有操作列表。 它使用 RE2 语法标准。 函数的作用是：*matchString()*报告作为参数传递的字符串是否包含正则表达式模式的任何匹配项。

**语法：**

```go
func MatchString(pattern string, s string)
```

**返回：**匹配的布尔值，错误

**示例：**

```go
// Golang program to illustrate the
// string matching using regexp
// in-built function
package main

import (
    "fmt"
    "regexp"
)

func main() {

    // string in which the pattern
    // is to be found
    str := "geeksforgeeks"

    // returns true if the pattern is present
    // in the string, else returns false
    // err is nil if the regexp is valid
    match1, err := regexp.MatchString("geeks", str)
    fmt.Println("Match: ", match1, " Error: ", err)

    // this returns false as the match
    // is unsuccessful
    str2 := "ComputerScience"
    match2, err := regexp.MatchString("geeks", str2)
    fmt.Println("Match: ", match2, "Error: ", err)

    // this will throw an error
    // as the pattern is not valid
    match3, err := regexp.MatchString("geek(s", str2)
    fmt.Println("Match: ", match3, "Error: ", err)
}
```

发帖主题：Re：Колибри0.7.0

```go
Match:  true  Error:  <nil>
Match:  false Error:  <nil>
Match:  false Error:  error parsing regexp: missing closing ): `geek(s`

```

为了存储复杂的正则表达式以备以后重用，**Compile()**方法解析正则表达式，如果解析成功，则返回一个 Regexp 对象，该对象可用于匹配文本。 该函数的原型为：

```go
func Compile(expr string) (*Regexp, error)
```

Regexp 包中还提供了其他各种方法来匹配字符串，如下所示：

```go
// Golang program to illustrate the
// string matching using regexp
// in-built functions
package main

import (
    "fmt"
    "regexp"
    "strings"
)

func main() {

    // a regex object which
    // can be reused later
    re, _ := regexp.Compile("geek")

    // string to be matched
    str := "I love geeksforgeeks"

    // returns the slice of first
    // and last index
    match := re.FindStringIndex(str)
    fmt.Println(match)

    str2 := "I love computer science"

    // prints an empty slice
    // as there is no match
    match2 := re.FindStringIndex(str2)
    fmt.Println(match2)

    // finds the first or leftmost
    // match to a given pattern.
    re2, _ := regexp.Compile("[0-9]+-v.*g")

    // matches one or more numbers followed
    // by v and any number of characters upto g
    match3 := re2.FindString("20024-vani_gupta")
    fmt.Println(match3)

    // returns a slice of all successive
    // matches of the expression
    match4 := re.FindAllStringSubmatchIndex("I'am a geek at"+
                                        " geeksforgeeks", -1)
    fmt.Println(match4)

    // returns a copy and replaces
    // matches with the replacement string
    re3, _ := regexp.Compile(" ")
    match5 := re3.ReplaceAllString("All I do"+
                    " is code everytime.", "+")
    fmt.Println(match5)

    // returns a copy in which all matches are
    // replaced by return value of function
    re4, _ := regexp.Compile("[aeiou]+")
    match6 := re4.ReplaceAllStringFunc("All I do"+
           " is code everytime.", strings.ToUpper)
    fmt.Println(match6)
}
```

发帖主题：Re：Колибри0.7.0

```go
[7 11]
[]
20024-vani_g
[[7 11] [15 19] [23 27]]
All+I+do+is+code+everytime.
All I dO Is cOdE EvErytImE.

```