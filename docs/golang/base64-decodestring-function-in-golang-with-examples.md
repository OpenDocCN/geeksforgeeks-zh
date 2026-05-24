# base64。Golang 中的去破坏()函数示例

> 原文:[https://www . geesforgeks . org/base64-去破坏-函数-在 golang-with-examples/](https://www.geeksforgeeks.org/base64-decodestring-function-in-golang-with-examples/)

Go 语言提供了对 base64 编码/解码的内置支持，并具有可用于使用 base64 包对给定数据执行操作的功能。这个包提供了**去破坏()**函数，用于将 base64 字符串解码为明文形式。它支持使用标准和网址兼容的 base64 标准进行解码。

**语法:**

```go
func (enc *Encoding) DecodeString(s string) ([]byte, error)
```

解码器使用的编码类型有 4 种变化:

*   **标准编码:**这是 RFC 4648 标准定义的标准编码。
*   **RawStdEncoding:** 这是 RFC 4648 标准定义的标准编码，只是省略了填充字符。
*   **网址编码:**这是 RFC 4648 标准定义的网址编码。它通常用于编码网址和文件名。
*   **rawurlending:**这是 RFC 4648 标准定义的要使用的网址编码。它通常用于编码网址和文件名，只是省略了填充字符。

**返回值:**返回给定 base64 字符串表示的字节数。

以下程序说明了**去破坏()**功能:

**例 1:**

```go
// Golang program to illustrate
// the base64.DecodeString() Function
package main

import (
    "encoding/base64"
    "fmt"
)

func main() {

    // taking a string
    givenString := "R2Vla3Nmb3JHZWVrcw=="

    // using the function
    decodedString, err := base64.StdEncoding.DecodeString(givenString)
    if err != nil {
        fmt.Println("Error Found:", err)
        return
    }

    fmt.Print("Decoded Bytes: ")
    fmt.Println(decodedString)

    fmt.Print("Decoded String: ")
    fmt.Println(string(decodedString))
}
```

**输出:**

```go
Decoded Bytes: [71 101 101 107 115 102 111 114 71 101 101 107 115]
Decoded String: GeeksforGeeks

```

**例 2:**

```go
// Golang program to illustrate
// the base64.DecodeString() Function
package main

import (
    "encoding/base64"
    "fmt"
)

func main() {

    // taking a string
    givenString := "aHR0cHM6Ly93d3cuZ2Vla3Nmb3JnZWVrcy5vcmcv"

    // using the function
    decodedString, err := base64.URLEncoding.DecodeString(givenString)
    if err != nil {
        fmt.Println("Error Found:", err)
        return
    }

    fmt.Print("Decoded Bytes: ")
    fmt.Println(decodedString)

    fmt.Print("Decoded String: ")
    fmt.Println(string(decodedString))
}
```

**输出:**

> 解码字节:[104 116 116 112 115 58 47 47 119 119 119 46 103 101 101 107 115 102 111 114 103 101 107 115 46 111 114 103 47]
> 解码字符串:https://www.geeksforgeeks.org/