# Golang 中的

# strcom.AppendUint()函数，示例为

> Original: [https://www.geeksforgeeks.org/strconv-appenduint-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strconv-appenduint-function-in-golang-with-examples/)

Go 语言提供内置支持，通过 strconv 包实现基本数据类型的字符串表示形式之间的转换。 此包提供了一个**AppendUint()函数**，用于将 FormatUint 生成的无符号整数 x 的字符串形式附加到 num 并返回扩展缓冲区。 或者换句话说，该函数将 uint 类型的整数 x 转换为字符串，并将其附加到 num 的末尾。 要访问**AppendUint()函数**，您需要在程序中导入 strconv 包。

**语法：**

```go
func AppendUint(num []byte, x uint64, base int) []byte
```

**示例 1：**

```go
// Golang program to illustrate
// strconv.AppendUint() function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Converting the unit
    // type integer x to a string
    // appends it to the end of
    // the given []byte
    // Using AppendUint() function
    val1 := []byte("uint value (base 16): ")
    val1 = strconv.AppendUint(val1, 35, 16)
    fmt.Println(string(val1))

    val2 := []byte("uint value (base 10): ")
    val2 = strconv.AppendUint(val2, 35, 10)
    fmt.Println(string(val2))

}
```

发帖主题：Re：Колибри0.7.0

```go
uint value (base 16): 23
uint value (base 10): 35

```

**示例 2：**

```go
// Golang program to illustrate
// strconv.AppendUint() function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Converting the unit 
    // type integer x to a string
    // appends it to the 
    // end of the given []byte
    // Using AppendUint() function
    val1 := []byte("uint value (base 16): ")
    val1 = strconv.AppendUint(val1, 45, 16)
    fmt.Println(string(val1))
    fmt.Println("Length: ", len(val1))
    fmt.Println("Capacity: ", cap(val1))

    val2 := []byte("uint value (base 10): ")
    val2 = strconv.AppendUint(val2, 43, 10)
    fmt.Println(string(val2))
    fmt.Println("Length: ", len(val2))
    fmt.Println("Capacity: ", cap(val2))

}
```

发帖主题：Re：Колибри0.7.0

```go
uint value (base 16): 2d
Length:  24
Capacity:  48
uint value (base 10):43
Length:  23
Capacity:  48

```