# strconv。Golang 中的 AppendBool()函数示例

> 原文:[https://www . geesforgeks . org/strconv-append bool-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strconv-appendbool-function-in-golang-with-examples/)

Go 语言通过 **strconv Package** 提供内置的支持来实现基本数据类型的字符串表示之间的转换。这个包提供了一个 **AppendBool()函数**，用于根据 num2 到 num1 的值追加 Bool(即真或假)，并返回扩展缓冲区，如语法所示。要访问 AppendBool()函数，您需要在程序中导入 strconv Package。

**语法:**

```go
func AppendBool(num1 []byte, num2 bool) []byte
```

**例 1:**

```go
// Golang program to illustrate
// strconv.AppendBool() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Using AppendBool() function
    val := []byte("Is Bool: ")
    val = strconv.AppendBool(val, true)

    fmt.Println(string(val))

}
```

**输出:**

```go
Is Bool: true
```

**例 2:**

```go
// Golang program to illustrate
// strconv.AppendBool() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Using AppendBool() function
    val := []byte("Append Bool:")
    fmt.Println(string(val))

    fmt.Println("Length(Before): ", len(val))
    fmt.Println("Capacity(Before): ", cap(val))

    val = strconv.AppendBool(val, true)
    fmt.Println(string(val))

    fmt.Println("Length(After): ", len(val))
    fmt.Println("Capacity(After): ", cap(val))

}
```

**输出:**

```go
Append Bool:
Length(Before):  12
Capacity(Before):  12
Append Bool:true
Length(After):  16
Capacity(After):  32

```