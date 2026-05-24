# Golang 中的 string s.SplitN()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-splitn-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-splitn-function-in-golang-with-examples/)

**字符串。SplitN()函数()**是围棋语言中的字符串操作函数。 它用于将给定字符串拆分成由分隔符分隔的子字符串。 此函数返回这些分隔符之间的所有子字符串的切片。

> **语法：**
> 
> ```go
> func SplitN(s, sep string, n int) []string
> ```
> 
> 这里，s 是字符串，sep 是分隔符。 如果 s 不包含给定的 Sep，并且 Sep 为非空，则它将返回长度为 1 的切片，该切片仅包含 s。或者，如果 Sep 为空，则它将在每个 UTF-8 序列之后拆分。 或者，如果 s 和 sep 都为空，则它将返回空片。
> 
> 这里，最后一个参数确定函数要返回的字符串数。 它可以是以下任一项：
> 
> *   N 等于零(n==0)：结果为零，即零子字符串。 返回一个空列表。
> *   N 大于零(n>0)：最多返回 n 个子字符串，最后一个字符串是未拆分的余数。
> *   N 小于零(n<0)：将返回所有可能的子字符串。

**示例 1：**

```go
// Golang program to illustrate the
// strings.SplitN() Function
package main

import (
    "fmt"
    "strings"
)

func main() {

    // String s a is comma serparated string
    // The separater used is ","
    // This will split the string into 6 parts
    s := strings.SplitN("a,b,c,d,e,f", ",",6)
    fmt.Println(s)
}
```

发帖主题：Re：Колибри0.7.0

```go
[a b c d e f]

```

**示例 2：**

```go
// Golang program to illustrate the
// strings.SplitN() Function
package main

import (
    "fmt"
    "strings"
)

func main() {

    // String s will be separated by spaces
    // -1 implies all the possible sub strings
    // that can be generated
    s := strings.SplitN("I love GeeksforGeeks portal!", " ", -1)

    // This will print all the sub strings
    // of string s in a new line
    for _, v := range s {
        fmt.Println(v)
    }
}
```

发帖主题：Re：Колибри0.7.0

```go
I
love
GeeksforGeeks
portal!

```

**示例 3：**

```go
// Golang program to illustrate the
// strings.SplitN() Function
package main

import (
    "fmt"
    "strings"
)

func main() {

    // This will give empty sub string
    // as 0 is provided as the last parameter
    s := strings.SplitN("a,b,c", ",", 0)
    fmt.Println(s)

    // This will give only 3 sub strings
    // a and b will be the first 2 sub strings
    s = strings.SplitN("a:b:c:d:e:f", ":", 3)
    fmt.Println(s)

    // Delimiter can be anything
    // a -ve number specifies all sub strings
    s = strings.SplitN("1234x5678x1234x5678", "x", -1)
    fmt.Println(s)

    // When the separator is not present in
    // given list, original string is returned
    s = strings.SplitN("qwerty", ",", 6)
    fmt.Println(s)
}
```

发帖主题：Re：Колибри0.7.0

```go
[]
[a b c:d:e:f]
[1234 5678 1234 5678]
[qwerty]

```