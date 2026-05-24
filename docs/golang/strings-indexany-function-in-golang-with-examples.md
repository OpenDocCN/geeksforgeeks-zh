# Golang 中的 strings.IndexAny()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-indexany-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-indexany-function-in-golang-with-examples/)

Golang 中的函数用于从原始字符串中的字符返回任何 Unicode 代码点的第一个实例的索引。 如果字符中的 Unicode 代码点在原始字符串中不可用，则此方法将返回-1。

**语法：**

```go
func IndexAny(str, charstr string) int
```

这里，str 是原始字符串，charstr 是我们要查找索引值的字符的 Unicode 代码点。

**示例 1：**

```go
// Golang program to illustrate
// the strings.IndexAny() Function
package main 

import ( 
    "fmt"
    "strings"
) 

// Main function 
func main() { 

    // Creating and initializing the strings 
    str1 := "GeeksforGeeks - A Computer Science Portal"
    str2 := "GFG is the Best"

    // Displaying strings 
    fmt.Println("String 1: ", str1) 
    fmt.Println("String 2: ", str2) 

    // Finding the index value 
    // of the given strings 
    // Using IndexAny() function 
    res1 := strings.IndexAny(str1, "G") 
    res2 := strings.IndexAny(str2, "Be") 
    res3 := strings.IndexAny("GFG, geeks", "uywq") 

    // Displaying the result 
    fmt.Println("\nIndex values:") 
    fmt.Println("Result 1: ", res1) 
    fmt.Println("Result 2: ", res2) 
    fmt.Println("Result 3: ", res3) 

} 
```

发帖主题：Re：Колибри0.7.0

```go
String 1:  GeeksforGeeks - A Computer Science Portal
String 2:  GFG is the Best

Index values:
Result 1:  0
Result 2:  9
Result 3:  -1

```

**示例 2：**

```go
// Golang program to illustrate
// the strings.IndexAny() Function
package main 

import ( 
    "fmt"
    "strings"
) 

// Main function 
func main() { 

    // using the function
    fmt.Println(strings.IndexAny("Why GFG?", "F")) 

} 
```

发帖主题：Re：Колибри0.7.0

```go
5

```