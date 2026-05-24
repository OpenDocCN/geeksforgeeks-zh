# 如何在格朗反转一根弦？

> 原文:[https://www . geesforgeks . org/如何反转 golang 中的字符串/](https://www.geeksforgeeks.org/how-to-reverse-a-string-in-golang/)

给定一个字符串，任务是反转该字符串。这里有几个例子。

**方法 1:** 通过交换字母来反转字符串，如第一个与最后一个，第二个与第二个与最后一个，以此类推。

**示例:**

```go
// Golang program to reverse a string
package main

// importing fmt
import "fmt"

// function, which takes a string as
// argument and return the reverse of string.
func reverse(s string) string {
    rns := []rune(s) // convert to rune
    for i, j := 0, len(rns)-1; i < j; i, j = i+1, j-1 {

        // swap the letters of the string,
        // like first with last and so on.
        rns[i], rns[j] = rns[j], rns[i]
    }

    // return the reversed string.
    return string(rns)
}

func main() {

    // Reversing the string.
    str := "Geeks"

    // returns the reversed string.
    strRev := reverse(str)
    fmt.Println(str)
    fmt.Println(strRev)
}
```

**输出:**

```go
Geeks
skeeG

```

**方法 2:** 本示例声明一个空字符串，然后开始从末尾开始逐个追加字符。

**示例:**

```go
// Golang program to reverse a string
package main

// importing fmt
import "fmt"

// function, which takes a string as
// argument and return the reverse of string.
func reverse(str string) (result string) {
    for _, v := range str {
        result = string(v) + result
    }
    return
}

func main() {

    // Reversing the string.
    str := "Geeks"

    // returns the reversed string.
    strRev := reverse(str)
    fmt.Println(str)
    fmt.Println(strRev)
}
```

**输出:**

```go
Geeks
skeeG

```