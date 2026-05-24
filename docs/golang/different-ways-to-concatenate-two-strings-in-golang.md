# 在 Golang 中连接两个字符串的不同方式

> 原文:[https://www . geeksforgeeks . org/different-way-concatenate-two-string-in-golang/](https://www.geeksforgeeks.org/different-ways-to-concatenate-two-strings-in-golang/)

在 Go 语言中，字符串是由任意字节组成的不可变链，用 UTF-8 编码进行编码。在 Go 字符串中，将两个或多个字符串添加到新的单个字符串中的过程称为串联。在 Go 语言中连接两个或多个字符串的最简单方法是使用`+ operator`。它也被称为连接运算符。

**示例:**

```go
// Go program to illustrate
// how to concatenate strings
package main

import "fmt"

func main() {

    // Creating and initializing strings
    // using var keyword
    var str1 string
    str1 = "Welcome!"

    var str2 string
    str2 = "GeeksforGeeks"

    // Concatenating strings
    // Using + operator
    fmt.Println("New string 1: ", str1+str2)

    // Creating and initializing strings
    // Using shorthand declaration
    str3 := "Geeks"
    str4 := "Geeks"

    // Concatenating strings
    // Using + operator
    result := str3 + "for" + str4

    fmt.Println("New string 2: ", result)

}
```

**输出:**

```go
New string 1:  Welcome!GeeksforGeeks
New string 2:  GeeksforGeeks

```

#### 连接字符串的其他方法

*   **Using bytes.Buffer:** You can also create a string by concatenating the bytes of the strings using `bytes.Buffer` with *WriteString() method*. It is defined under bytes package. It prevents the generation of the unnecessary string object, means it doesn’t generate a new string like in + operator from two or more strings.

    **示例:**

    ```go
    // Go program to illustrate how to concatenate strings
    // Using bytes.Buffer with WriteString() function
    package main

    import (
        "bytes"
        "fmt"
    )

    func main() {

        // Creating and initializing strings
        // Using bytes.Buffer with 
        // WriteString() function
        var b bytes.Buffer

        b.WriteString("G")
        b.WriteString("e")
        b.WriteString("e")
        b.WriteString("k")
        b.WriteString("s")

        fmt.Println("String: ", b.String())

        b.WriteString("f")
        b.WriteString("o")
        b.WriteString("r")
        b.WriteString("G")
        b.WriteString("e")
        b.WriteString("e")
        b.WriteString("k")
        b.WriteString("s")

        fmt.Println("String: ", b.String())

    }
    ```

    **输出:**

    ```go
    String:  Geeks
    String:  GeeksforGeeks

    ```

*   **Using Sprintf:** In Go language, you can also concatenate string using *Sprintf()* method.

    **示例:**

    ```go
    // Go program to illustrate how to concatenate strings
    // Using Sprintf function
    package main

    import "fmt"

    func main() {

        // Creating and initializing strings
        str1 := "Tutorial"
        str2 := "of"
        str3 := "Go"
        str4 := "Language"

        // Concatenating strings using 
        // Sprintf() function
        result := fmt.Sprintf("%s%s%s%s", str1, 
                              str2, str3, str4)

        fmt.Println(result)
    }
    ```

    **输出:**

    ```go
    TutorialofGoLanguage
    ```

*   **Using += operator or String append:** In Go strings, you are allowed to append a string using *+= operator*. This operator adds a new or given string to the end of the specified string.

    **示例:**

    ```go
    // Go program to illustrate how
    // to concatenate strings
    // Using += operator
    package main

    import "fmt"

    func main() {

        // Creating and initializing strings
        str1 := "Welcome"
        str2 := "GeeksforGeeks"

        // Using += operator
        str1 += str2
        fmt.Println("String: ", str1)

        str1 += "This is the tutorial of Go language"
        fmt.Println("String: ", str1)

        str2 += "Portal"
        fmt.Println("String: ", str2)

    }
    ```

    **输出:**

    ```go
    String:  WelcomeGeeksforGeeks
    String:  WelcomeGeeksforGeeksThis is the tutorial of Go language
    String:  GeeksforGeeksPortal

    ```

*   **Using Join() function:** This function concatenates all the elements present in the slice of string into a single string. This function is available in string package.

    **语法:**

    ```go
    func Join(str []string, sep string) string
    ```

    这里， *str* 是我们可以连接元素的字符串，sep 是放置在最终字符串中元素之间的分隔符。

    **示例:**

    ```go
    // Go program to illustrate how to
    // concatenate all the elements
    // present in the slice of the string
    package main

    import (
        "fmt"
        "strings"
    )

    func main() {

        // Creating and initializing slice of string
        myslice := []string{"Welcome", "To",
                  "GeeksforGeeks", "Portal"}

        // Concatenating the elements 
        // present in the slice
        // Using join() function
        result := strings.Join(myslice, "-")
        fmt.Println(result)
    }
    ```

    **输出:**

    ```go
    Welcome-To-GeeksforGeeks-Portal
    ```