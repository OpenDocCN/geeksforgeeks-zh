# Golang 中的 Strings.FieldsFunc()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-fieldsfunc-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-fieldsfunc-function-in-golang-with-examples/)

Golang 中的函数用于在每次运行满足 f(C)的 Unicode 代码点 c 时拆分给定的字符串字符串，并返回一个字符串切片数组。

> **语法：**
> 
> ```go
> func FieldsFunc(str string, f func(rune) bool) []string
> ```
> 
> 这里，*str*是给定的字符串，rune 是内置类型，用于包含单个 Unicode 字符，f 是用户定义的函数。
> 
> **返回：**如果字符串中的所有代码点都满足 f(C)或字符串为空，则返回空片。

**注意：**此函数不保证其调用 f(C)的顺序。 如果 f 没有为给定的 c 返回一致的结果，FieldsFunc 可能会崩溃。

**示例 1：**

```go
// Golang program to illustrate the
// strings.FieldsFunc() Function

package main

import (
    "fmt"
    "strings"
    "unicode"
)

func main() {

    // f is a function which returns true if the
    // c is number and false otherwise
    f := func(c rune) bool {
        return unicode.IsNumber(c)
    }

    // FieldsFunc() function splits the string passed
    // on the return values of the function f
    // String will therefore be split when a number
    // is encontered and returns all non-numbers
    fmt.Printf("Fields are: %q\n", 
       strings.FieldsFunc("ABC123PQR456XYZ789", f))
}
```

发帖主题：Re：Колибри0.7.0

```go
Fields are: ["ABC" "PQR" "XYZ"]
```

**示例 2：**

```go
// Golang program to illustrate the
// strings.FieldsFunc() Function
package main

import (
    "fmt"
    "strings"
    "unicode"
)

func main() {

    // f is a function which returns true if the
    // c is a white space or a full stop
    // and returns false otherwise
    f := func(c rune) bool {
        return unicode.IsSpace(c) || c == '.'
    }

    // We can also pass a string indirectly
    // The string will split when a space or a
    // full stop is encontered and returns all non-numbers
    s := "We are humans. We are social animals."
    fmt.Printf("Fields are: %q\n", strings.FieldsFunc(s, f))
}
```

发帖主题：Re：Колибри0.7.0

```go
Fields are: ["We" "are" "humans" "We" "are" "social" "animals"]
```