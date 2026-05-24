# Golang 中的

# strconv.AppendInt（）函数及示例

> 原文： [https://www.geeksforgeeks.org/strconv-appendint-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strconv-appendint-function-in-golang-with-examples/)

Go 语言提供内置支持，通过**strconv 包**实现与基本数据类型字符串表示的转换。该包提供**AppendInt（）函数**用于将 FormatInt 生成的整数 val 的字符串形式追加到 num，并返回扩展缓冲区，如下语法所示。要访问 AppendInt（）函数，需要在程序中导入 strconv 包。

**语法：**

```go
func AppendInt(num []byte, val int64, base int) []byte
```

**例 1:**

```go
// Golang program to illustrate
// strconv.AppendInt() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Using AppendInt() function
    val1 := []byte("int value(base 10): ")
    val1 = strconv.AppendInt(val1, -35, 10)
    fmt.Println(string(val1))

    val2 := []byte("int value(base 16): ")
    val2 = strconv.AppendInt(val2, -44, 16)
    fmt.Println(string(val2))

}
```

**输出：**

```go
int value(base 10): -35
int value(base 16): -2c

```

**例 2:**

```go
// Golang program to illustrate
// strconv.AppendInt() Function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Using AppendInt() function
    val1 := []byte("int value(base 10): ")
    val1 = strconv.AppendInt(val1, 45, 10)

    fmt.Println(string(val1))
    fmt.Println("Length: ", len(val1))
    fmt.Println("Capacity: ", cap(val1))

    val2 := []byte("int value(base 16): ")
    val2 = strconv.AppendInt(val2, 42, 16)

    fmt.Println(string(val2))
    fmt.Println("Length: ", len(val2))
    fmt.Println("Capacity: ", cap(val2))

}
```

**输出：**

```go
int value(base 10): 45
Length:  22
Capacity:  48
int value(base 16): 2a
Length:  22
Capacity:  48

```