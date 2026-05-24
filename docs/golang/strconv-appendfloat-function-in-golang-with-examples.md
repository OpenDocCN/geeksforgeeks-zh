# strconv。Golang 中的 AppendFloat()函数示例

> 原文:[https://www . geesforgeks . org/strconv-appendfloat-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strconv-appendfloat-function-in-golang-with-examples/)

Go 语言通过 **strconv Package** 提供内置的支持来实现基本数据类型的字符串表示之间的转换。这个包提供了一个 **AppendFloat()函数**，用来追加浮点数的字符串形式。要访问 AppendFloat()函数，您需要在程序中导入 strconv Package。

**语法:**

```go
func AppendFloat(num []byte, val float64, fmt byte, prec, bitSize int) []byte
```

这个函数将把由 FormatFloat 生成的浮点数 val 的字符串形式附加到 num，并返回扩展缓冲区。

**例 1:**

```go
// Golang program to illustrate
// strconv.AppendFloat() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Using AppendFloat() function
    val1 := []byte("Float32 value: ")
    val1 = strconv.AppendFloat(val1, 4.5683568954, 'E', -1, 32)
    fmt.Println(string(val1))

    val2 := []byte("Float64 value: ")
    val2 = strconv.AppendFloat(val2, 6.7415678653, 'E', -1, 64)
    fmt.Println(string(val2))

}
```

**输出:**

```go
Float32 value: 4.568357E+00
Float64 value: 6.7415678653E+00

```

**例 2:**

```go
// Golang program to illustrate
// strconv.AppendFloat() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Using AppendFloat() function
    val1 := []byte("Float32 value: ")
    val1 = strconv.AppendFloat(val1, 
          5.5636895645, 'E', -1, 32)

    fmt.Println(string(val1))

    // using len and cap function
    fmt.Println("Length: ", len(val1))
    fmt.Println("Capacity: ", cap(val1))

    val2 := []byte("Float64 value: ")
    val2 = strconv.AppendFloat(val2,
        1.741532678653, 'E', -1, 64)

    fmt.Println(string(val2))

    // using len and cap function
    fmt.Println("Length: ", len(val2))
    fmt.Println("Capacity: ", cap(val2))

}
```

**输出:**

```go
Float32 value: 5.5636897E+00
Length:  28
Capacity:  32
Float64 value: 1.741532678653E+00
Length:  33
Capacity:  64

```