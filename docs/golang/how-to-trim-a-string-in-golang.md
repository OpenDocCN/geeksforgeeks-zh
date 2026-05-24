# 如何在 Golang 修剪一根弦？

> 原文:[https://www . geesforgeks . org/如何在 golang 中修剪字符串/](https://www.geeksforgeeks.org/how-to-trim-a-string-in-golang/)

在 Go 语言中，字符串不同于其他语言，如 [Java](https://www.geeksforgeeks.org/java/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Python](https://www.geeksforgeeks.org/python-programming-language/) 等。它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。您可以使用以下函数列表以不同的方式修剪字符串。所有这些函数都是在 strings package 下定义的，因此您必须在程序中导入 strings package 才能访问这些函数。

**1。修剪:**此函数用于修剪字符串中所有在此函数中指定的前导和尾随 Unicode 代码点。

**语法:**

```go
func Trim(str string, cutstr string) string
```

这里， *str* 代表当前字符串， *cutstr* 代表要在给定字符串中修剪的元素。

**示例:**

```go
// Go program to illustrate 
// how to trim a string
package main

import (
    "fmt"
    "strings"
)

// Main method
func main() {

    // Creating and initializing string
    // Using shorthand declaration
    str1 := "!!Welcome to GeeksforGeeks !!"
    str2 := "@@This is the tutorial of Golang$"

    // Displaying strings
    fmt.Println("Strings before trimming:")
    fmt.Println("String 1: ", str1)
    fmt.Println("String 2:", str2)

    // Trimming the given strings
    // Using Trim() function
    res1 := strings.Trim(str1, "!")
    res2 := strings.Trim(str2, "@{content}quot;)

    // Displaying the results
    fmt.Println("\nStrings after trimming:")
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2:", res2)
}
```

**输出:**

```go
Strings before trimming:
String 1:  !!Welcome to GeeksforGeeks !!
String 2: @@This is the tutorial of Golang$

Strings after trimming:
Result 1:  Welcome to GeeksforGeeks 
Result 2: This is the tutorial of Golang

```

**2。TrimLeft:** 此函数用于修剪字符串的左侧(在函数中指定)Unicode 代码点。

**语法:**

```go
func TrimLeft(str string, cutstr string) string
```

这里， *str* 代表当前字符串， *cutstr* 代表您想要在给定字符串中修剪的左侧元素。

**示例:**

```go
// Go program to illustrate how to
// trim left-hand side elements
// from the string
package main

import (
    "fmt"
    "strings"
)

// Main method
func main() {

    // Creating and initializing string
    // Using shorthand declaration
    str1 := "!!Welcome to GeeksforGeeks **"
    str2 := "@@This is the tutorial of Golang$"

    // Displaying strings
    fmt.Println("Strings before trimming:")
    fmt.Println("String 1: ", str1)
    fmt.Println("String 2:", str2)

    // Trimming the given strings
    // Using TrimLeft() function
    res1 := strings.TrimLeft(str1, "!*")
    res2 := strings.TrimLeft(str2, "@")

    // Displaying the results
    fmt.Println("\nStrings after trimming:")
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2:", res2)
}
```

**输出:**

```go
Strings before trimming:
String 1:  !!Welcome to GeeksforGeeks **
String 2: @@This is the tutorial of Golang$

Strings after trimming:
Result 1:  Welcome to GeeksforGeeks **
Result 2: This is the tutorial of Golang$

```

**3。TrimRight:** 此函数用于修剪字符串的右侧(在函数中指定)Unicode 代码点。

**语法:**

```go
func TrimRight(str string, cutstr string) string
```

这里， *str* 代表当前字符串， *cutstr* 代表您想要在给定字符串中修剪的右侧元素。

**示例:**

```go
// Go program to illustrate how to
// trim right-hand side elements
// from the string
package main

import (
    "fmt"
    "strings"
)

// Main method
func main() {

    // Creating and initializing the
    // string using shorthand declaration
    str1 := "!!Welcome to GeeksforGeeks **"
    str2 := "@@This is the tutorial of Golang$"

    // Displaying strings
    fmt.Println("Strings before trimming:")
    fmt.Println("String 1: ", str1)
    fmt.Println("String 2:", str2)

    // Trimming the given strings
    // Using TrimRight() function
    res1 := strings.TrimRight(str1, "!*")
    res2 := strings.TrimRight(str2, "{content}quot;)

    // Displaying the results
    fmt.Println("\nStrings after trimming:")
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2:", res2)
}
```

**输出:**

```go
Strings before trimming:
String 1:  !!Welcome to GeeksforGeeks **
String 2: @@This is the tutorial of Golang$

Strings after trimming:
Result 1:  !!Welcome to GeeksforGeeks 
Result 2: @@This is the tutorial of Golang

```

**4。TrimSpace:** 该函数用于修剪指定字符串的所有前导和尾随空格。

**语法:**

```go
func TrimSpace(str string) string
```

**示例:**

```go
// Go program to illustrate how to
// trim white space from the string
package main

import (
    "fmt"
    "strings"
)

// Main method
func main() {

    // Creating and initializing string
    // Using shorthand declaration
    str1 := "   **Welcome to GeeksforGeeks**   "
    str2 := "  ##This is the tutorial of Golang##  "

    // Displaying strings
    fmt.Println("Strings before trimming:")
    fmt.Println(str1, str2)

    // Trimming white space from the given strings
    // Using TrimSpace() function
    res1 := strings.TrimSpace(str1)
    res2 := strings.TrimSpace(str2)

    // Displaying the results
    fmt.Println("\nStrings after trimming:")
    fmt.Println(res1, res2)
}
```

**输出:**

```go
Strings before trimming:
   **Welcome to GeeksforGeeks**      ##This is the tutorial of Golang##  

Strings after trimming:
**Welcome to GeeksforGeeks** ##This is the tutorial of Golang##

```

**5。TrimSuffix:** 此方法用于从给定字符串中修剪尾部后缀字符串。如果给定的字符串不包含指定的后缀字符串，则此函数返回原始字符串，不做任何更改。

**语法:**

```go
func TrimSuffix(str, suffstr string) string
```

这里， *str* 代表原始字符串， *suffstr* 代表后缀字符串。

**示例:**

```go
// Go program to illustrate how to
// trim a suffix string from the
// given string
package main

import (
    "fmt"
    "strings"
)

// Main method
func main() {

    // Creating and initializing string
    // Using shorthand declaration
    str1 := "Welcome, GeeksforGeeks"
    str2 := "This is the, tutorial of Golang"

    // Displaying strings
    fmt.Println("Strings before trimming:")
    fmt.Println("String 1: ", str1)
    fmt.Println("String 2:", str2)

    // Trimming suffix string from the given strings
    // Using TrimSuffix() function
    res1 := strings.TrimSuffix(str1, "GeeksforGeeks")
    res2 := strings.TrimSuffix(str2, "Hello")

    // Displaying the results
    fmt.Println("\nStrings after trimming:")
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2:", res2)
}
```

**输出:**

```go
Strings before trimming:
String 1:  Welcome, GeeksforGeeks
String 2: This is the, tutorial of Golang

Strings after trimming:
Result 1:  Welcome, 
Result 2: This is the, tutorial of Golang

```

**6。TrimPrefix:** 该方法用于从给定字符串中修剪前导前缀字符串。如果给定的字符串不包含指定的前缀字符串，则此函数返回原始字符串，不做任何更改。

**语法:**

```go
func TrimPrefix(str, suffstr string) string
```

这里， *str* 代表原始字符串， *suffstr* 代表前缀字符串。

**示例:**

```go
// Go program to illustrate how to
// trim the prefix string from the
// given string
package main

import (
    "fmt"
    "strings"
)

// Main method
func main() {

    // Creating and initializing string
    // Using shorthand declaration
    str1 := "Welcome, GeeksforGeeks"
    str2 := "This is the, tutorial of Golang"

    // Displaying strings
    fmt.Println("Strings before trimming:")
    fmt.Println("String 1: ", str1)
    fmt.Println("String 2: ", str2)

    // Trimming prefix string from the given strings
    // Using TrimPrefix() function
    res1 := strings.TrimPrefix(str1, "Welcome")
    res2 := strings.TrimPrefix(str2, "Hello")

    // Displaying the results
    fmt.Println("\nStrings after trimming:")
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)
}
```

**输出:**

```go
Strings before trimming:
String 1:  Welcome, GeeksforGeeks
String 2:  This is the, tutorial of Golang

Strings after trimming:
Result 1:  , GeeksforGeeks
Result 2:  This is the, tutorial of Golang

```