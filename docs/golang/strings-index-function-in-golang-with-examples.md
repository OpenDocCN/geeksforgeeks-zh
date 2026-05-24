# Golang 中的 string s.Index()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-index-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-index-function-in-golang-with-examples/)

Golang 中的函数用于获取指定子字符串的第一个实例。 如果没有找到子字符串，则此方法将返回-1。

**语法：**

```go
func Index(str, sbstr string) int
```

这里，str 是原始字符串，sbstr 是我们要查找其索引值的字符串。

**示例 1：**

```go
// Go program to illustrate the 
// String Index() Function

package main 

import ( 
    "fmt"
    "strings"
) 

// Main function 
func main() { 

    // Creating and initializing the strings 
    str1 := "Welcome to GeeksforGeeks"
    str2 := "My name is XYZ"

    // Displaying strings 
    fmt.Println("String 1: ", str1) 
    fmt.Println("String 2: ", str2) 

    // Using Index() function 
    res1 := strings.Index(str1, "Geeks") 
    res2 := strings.Index(str2, "is") 

    // Displaying the result 
    fmt.Println("\nIndex values:") 
    fmt.Println("Result 1: ", res1) 
    fmt.Println("Result 2: ", res2) 

} 
```

发帖主题：Re：Колибри0.7.0

```go
String 1:  Welcome to GeeksforGeeks
String 2:  My name is XYZ

Index values:
Result 1:  11
Result 2:  8

```

**示例 2：**

```go
// Go program to illustrate the
// String Index() Function

package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {

    // Using Index() function
    res1 := strings.Index("GFG", "H")
    res2 := strings.Index("GeeksforGeeks", "for")

    // Displaying the result
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)

}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1:  -1
Result 2:  5

```