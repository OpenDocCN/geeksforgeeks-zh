# 如何在 GoLang 中获取一个整型变量作为 String？

> 原文:[https://www . geeksforgeeks . org/如何以字符串形式获取整数变量/golang/](https://www.geeksforgeeks.org/how-to-fetch-an-integer-variable-as-string-in-golang/)

要获取一个整数变量作为[字符串](https://www.geeksforgeeks.org/strings-in-golang/)，Go 提供了 **strconv** 包，该包包含返回整型变量字符串表示的方法。没有什么比整数变量转换为字符串变量更好的了，相反，您必须将整数值存储为字符串变量中的字符串。以下是用于将整数转换为字符串的函数:

**1。strconv。Itoa():** 将一个 int 转换为十进制字符串。

```go
// s == "60"
s := strconv.Itoa(60) 

```

**2。strconv。格式化 Int():** 在给定的基数上格式化 int64。

```go
var n int64 = 60

s := strconv.FormatInt(n, 10)   // s == "60" (decimal)

s := strconv.FormatInt(n, 16)   // s == "3C" (hexadecimal)

```

**3。strconv。FormatUint():** 返回给定基数中 x 的字符串表示，即 2 < =基数< = 36。

```go
fmt.Println(strconv.FormatUint(60, 2)) // 111100 (binary)
fmt.Println(strconv.FormatUint(60, 10)) // 60 (decimal)

```

**例 1:**

```go
package main

import (
    "fmt"
    "strconv"
)

func main() {

    var var_int int
    var_int = 23

    // Itoa() is the most common
    // conversion from int to string.
    s1 := strconv.Itoa(var_int)
    fmt.Printf("%T %v\n", s1, s1)

    // format 23 int base 10 -> 23
    s2 := strconv.FormatInt(int64(var_int), 10)
    fmt.Printf("%T %v\n", s2, s2)

    // return string representation
    // of 23 in base 10 -> 23
    s3 := strconv.FormatUint(uint64(var_int), 10)
    fmt.Printf("%T %v\n", s3, s3)

    // concatenating all string->s1,s2 and s3.
    fmt.Println("Concatenating all strings: ", s1+s2+s3)
}
```

**输出:**

```go
string 23
string 23
string 23
Concatenating all strings: 232323

```

**例 2:**

```go
package main

import (
    "fmt"
    "strconv"
)

func main() {

    var var_int int
    var_int = 50

    // Itoa() is the most common 
    // conversion from int to string.
    s1 := strconv.Itoa(var_int)
    fmt.Printf("%T %v\n", s1, s1)

    // format 50 int base 2 ->110010
    s2 := strconv.FormatInt(int64(var_int), 2)
    fmt.Printf("%T %v\n", s2, s2)

    // return string representation
    // of 50 in base 16 -> 32
    s3 := strconv.FormatUint(uint64(var_int), 16)
    fmt.Printf("%T %v\n", s3, s3)

    // concatenating all
    // string->s1,s2 and s3.
    fmt.Println("Concatenating all strings: ", s1+s2+s3)
}
```

**输出:**

```go
string 50
string 110010
string 32
Concatenating all strings: 5011001032

```