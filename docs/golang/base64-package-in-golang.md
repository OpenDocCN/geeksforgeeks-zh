# 戈朗 base64 包装

> 原文:[https://www.geeksforgeeks.org/base64-package-in-golang/](https://www.geeksforgeeks.org/base64-package-in-golang/)

Go 语言提供了对 base64 编码/解码的内置支持，并具有可用于使用 base64 包对给定数据执行操作的功能。

| 功能 | 描述 |
| **新译码器** | 该函数用于构建一个新的 base64 流解码器。 |
| **新编码器** | 该函数用于返回一个新的 base64 流编码器。 |

**类型编码:**编码是由 64 个字符的字母表定义的基数为 64 的编码/解码方案。最常见的编码是 RFC 4648 中定义的“base64”编码，它用于 MIME (RFC 2045)和 PEM (RFC 1421)。RFC 4648 还定义了一种替代编码，这是标准编码，用–和 _ 替换+和/。

```go
type Encoding struct {
    // It holds filtered or unexported fields
}

```

| 方法 | 描述 |
| **func 新编码** | 此函数用于返回由给定字母表定义的新填充编码，它必须是不包含填充字符或 CR / LF ('\r '，' \n ')的 64 字节字符串。 |
| **功能(*编码)解码** | 此方法用于使用编码端解码 src。此方法最多将 decodelen(len(src))字节写入 dst，并返回写入的字节数。如果 src 包含无效的 base64 数据，则此方法将返回成功写入的字节数和腐败错误。这里，新的行字符(\r 和\n)被忽略。 |
| **功能(*编码)去破坏** | 此方法用于返回由 base64 字符串表示的字节。 |
| **函数(*编码)解码** | 此方法用于返回对应于 n 字节 base64 编码数据的解码数据的最大长度(以字节为单位)。 |
| **功能(*编码)编码** | 此方法用于使用编码 enc 对 src 进行编码，将 encodelen(len(src))字节写入 dst。 |
| **功能(*编码)编码字符串** | 此方法用于返回 src 的 base64 编码。 |
| **func(*编码)编码** | 此方法用于返回长度为 n 的输入缓冲区的 base64 编码的字节长度。 |
| **功能(编码)严格** | 此方法用于创建与 enc 相同的新编码，但启用了严格解码。 |
| **带填充功能(编码)** | 此方法用于创建一个与 enc 相同的新编码，除了指定的填充字符，或者 no add 禁用填充。 |

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

    // Taking a string
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
// the base64.NewEncoder() function
package main

import (
    "encoding/base64"
    "fmt"
)

func main() {

    // Input string
    giveninput := []byte("GeeksforGeeks")

    // Using EncodeToString() function
    // Encode the given string
    result := base64.StdEncoding.EncodeToString(giveninput)
    fmt.Println("Encoded string: ", result)
}
```

**输出:**

```go
Encoded string:  R2Vla3Nmb3JHZWVrcw==
```