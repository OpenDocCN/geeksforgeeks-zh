# Golang

中的 strconv 包

> Original: [https://www.geeksforgeeks.org/strconv-package-in-golang/](https://www.geeksforgeeks.org/strconv-package-in-golang/)

Go Language 提供了一个 strconv 包，它实现了与基本数据类型的字符串表示形式之间的转换。 要访问 strconv 包的功能，您需要在程序中借助 import 关键字导入 strconv 包。

的给定基数中 i 的字符串表示形式。的给定基数中 i 的字符串表示形式。=>=>

| 功能 / 目的 / 函数关系 | 描述 / 描写 / 形容 / 类别 |
| **[函数 AppendBool](https://www.geeksforgeeks.org/strconv-appendbool-function-in-golang-with-examples/)** | 此函数用于根据 x 的值将 TRUE 或 FALSE 附加到 DST，并返回扩展缓冲区。 |
| **[Func AppendFloat](https://www.geeksforgeeks.org/strconv-appendfloat-function-in-golang-with-examples/)** | 此函数用于将 FormatFloat 生成的浮点数 f 的字符串形式附加到 DST，并返回扩展缓冲区。 |
| **[函数 AppendInt](https://www.geeksforgeeks.org/strconv-appendint-function-in-golang-with-examples/)** | 此函数用于将 FormatInt 生成的整数 i 的字符串形式附加到 DST，并返回扩展缓冲区。 |
| 加入时间：清华大学 2007 年 01 月 25 日下午 3：33 | 此函数用于将由 Quote 生成的表示 s 的双引号 GO 字符串文字附加到 DST，并返回扩展缓冲区。 |
| 加入时间：清华大学 2007 年 01 月 25 日下午 3：33 | 此函数用于将 QuoteRune 生成的表示符文的单引号 GO 字符文字附加到 DST，并返回扩展缓冲区。 |
| Колибриобработаетсяпрограммированияпрограммированияпрограмможится | 此函数用于将 QuoteRuneToASCII 生成的表示符文的单引号 GO 字符文字附加到 DST，并返回扩展缓冲区。 |
| **函数 AppendQuoteRuneToGraphic** | 此函数用于将 QuoteRuneToGraphic 生成的表示符文的单引号 GO 字符文字附加到 DST，并返回扩展缓冲区。 |
| **[函数 AppendQuoteToASCII](https://www.geeksforgeeks.org/strconv-appendquotetoascii-function-in-golang-with-examples/)** | 此函数用于将 QuoteToASCII 生成的表示 s 的带双引号的 GO 字符串文字附加到 DST，并返回扩展缓冲区。 |
| **函数 AppendQuoteToGraphic** | 此函数用于将 QuoteToGraphic 生成的表示 s 的带双引号的 GO 字符串文字附加到 DST，并返回扩展缓冲区。 |
| **[函数 AppendUint](https://www.geeksforgeeks.org/strconv-appenduint-function-in-golang-with-examples/)** | 此函数用于将 FormatUint 生成的无符号整数 i 的字符串形式附加到 DST，并返回扩展缓冲区。 |
| **[函数 Atoi](https://www.geeksforgeeks.org/strconv-atoi-function-in-golang-with-examples/)** | 此函数等效于 ParseInt(s，10，0)，并转换为 int 类型。 |
| **[函数可反引号](https://www.geeksforgeeks.org/how-to-use-strconv-canbackquote-function-in-golang/)** | 此函数用于检查给定字符串是否可以原封不动地表示为不带制表符以外的控制字符的单行反引号字符串。 |
| **[函数 FormatBool](https://www.geeksforgeeks.org/how-to-use-strconv-formatbool-function-in-golang/)** | 此函数用于根据 x 的值返回 TRUE 或 FALSE。 |
| **函数格式浮动** | 此函数用于根据格式 fmt 和精度 prec 将浮点数 f 转换为字符串。 |
| **函数格式 Int** | 此函数用于返回 2<= base <="36. |
| **[函数格式](https://www.geeksforgeeks.org/how-to-use-strconv-formatuint-function-in-golang/)** | 此函数用于返回 2<= base <="36. |
| **函数等图形** | 此函数用于检查符文是否由 Unicode 定义为图形。 |
| **[函数 IsPrint](https://www.geeksforgeeks.org/how-to-use-strconv-isprint-function-in-golang/)** | 此函数用于检查符文是否定义为可通过 GO 打印，定义与 unicode.IsPrint：字母、数字、标点符号、符号和 ASCII 空格。 |
| **[函数 Itoa](https://www.geeksforgeeks.org/how-to-use-strconv-itoa-function-in-golang/)** | 此函数相当于 FormatInt(int64(I)，10)。 |
| **Func ParseBool** | 此函数用于返回字符串表示的布尔值。 |
| **函数解析浮动** | 此函数用于将字符串 s 转换为精度由 bitSize 指定的浮点数：32(对于 float32)或 64(对于 float64)。 |
| **Func ParseInt** | 此函数解释给定基数(0，2 到 36)和位大小(0 到 64)的字符串字符串，并返回相应的值 i。 |
| **func ParseUint** | 此函数类似于 ParseInt，但用于无符号数字。 |
| 加入时间：清华大学 2007 年 01 月 25 日下午 3：33 | 此函数用于返回表示 s 的双引号 go 字符串文字。 |
| 加入时间：清华大学 2007 年 01 月 25 日下午 3：33 | 此函数用于返回表示符文的单引号 GO 字符文字。 |
| Колибрипрограммированияпрограмме | 此函数用于返回表示符文的单引号 GO 字符文字。 |
| **Func QuoteRuneToGraphic** | 此函数用于返回表示符文的单引号 GO 字符文字。 |
| Колибрипрограммирования | 此函数用于返回表示 s 的双引号 go 字符串文字。 |
| **Func QuoteToGraphic** | 此函数用于返回表示 s 的双引号 go 字符串文字。 |
| **函数不引用** | 此函数将 s 解释为单引号、双引号或反引号 Go 字符串文字，返回 s 引号的字符串值。 |
| **函数 UnquteChar** | 此函数用于解码转义字符串或字符串 s 表示的字符文字中的第一个字符或字节。 |

**示例 1：**

```go
// Golang program to illustrate the 
// strconv.AppendQuoteRuneToASCII() function
package main

import (
    "fmt"
    "strconv"
)

func main() {

         // Converting Unicode characters to 
         // ASCII strings resulting from "single quotes"
         // append the result to the end of the given []byte
         // Using AppendQuoteRuneToASCII() function
         num := []byte("Rune : ")
         num = strconv.AppendQuoteRuneToASCII(num, 'c')
         fmt.Println(string(num))

}
```

发帖主题：Re：Колибри0.7.0

```go
Rune : 'c'
```

**示例 2：**

```go
// Golang program to illustrate 
// strconv.Atoi() function 
package main 

import ( 
    "fmt"
    "strconv"
) 

func main() { 

    // Using Atoi() function 
    a := "244"
    b, e := strconv.Atoi(a) 
    if e == nil { 
        fmt.Printf("%T \n %v", b, b) 
    } 

} 
```

发帖主题：Re：Колибри0.7.0

```go
int 
 244

```