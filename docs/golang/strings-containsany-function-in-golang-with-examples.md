# Golang 中的 string s.ContainsAny()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-containsany-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-containsany-function-in-golang-with-examples/)

ContainsAny 函数用于检查字符串中是否存在字符形式的 Unicode 代码点。 它是一个内置函数，用于查找字符串中是否存在指定的字符串，如果找到，则返回 TRUE 或 FALSE。

**语法：**

```go
func ContainsAny(str, charstr string) bool

```

这里，第一个参数是原始字符串，第二个参数是要在字符串中找到的子字符串或一组字符。 即使在字符串中找到子字符串中的一个字符，该函数也会返回 TRUE。 该函数根据输入返回布尔值，即 TRUE/FALSE。

**示例：**

```go
// Go program to illustrate how to check whether
// the string is present or not in the specified string
package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {

    // Creating and initializing strings
    str1 := "Welcome to Geeks for Geeks"
    str2 := "We are here to learn about go strings"

    // Checking the string present or 
    // not using the ContainsAny() function
    res1 := strings.ContainsAny(str1, "Geeks")
    res2 := strings.ContainsAny(str2, "GFG")
    res3 := strings.ContainsAny("GeeksforGeeks", "Gz")
    res4 := strings.ContainsAny("GeeksforGeeks", "ue")
    res5 := strings.ContainsAny("GeeksforGeeks", " ")

    // Displaying the output
    fmt.Println("\nResult 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)
    fmt.Println("Result 4: ", res4)
    fmt.Println("Result 5: ", res5)

}
```

发帖主题：Re：Колибри0.7.8.0