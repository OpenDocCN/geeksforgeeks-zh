# Golang中的strconv包

> Original: [https://www.geeksforgeeks.org/strconv-package-in-golang/](https://www.geeksforgeeks.org/strconv-package-in-golang/)

Go语言提供了一个`strconv`包，它实现了与基本数据类型的字符串表示形式之间的转换。要访问`strconv`包的功能，您需要在程序中借助`import`关键字导入`strconv`包。

| 功能 / 目的 / 函数关系 | 描述 / 描写 / 形容 / 类别 |
| --- | --- |
| `AppendBool`函数 | 此函数用于根据`x`的值将`TRUE`或`FALSE`附加到`dst`，并返回扩展缓冲区。 |
| `AppendFloat`函数 | 此函数用于将`FormatFloat`生成的浮点数`f`的字符串形式附加到`dst`，并返回扩展缓冲区。 |
| `AppendInt`函数 | 此函数用于将`FormatInt`生成的整数`i`的字符串形式附加到`dst`，并返回扩展缓冲区。 |
| `AppendQuote`函数 | 此函数用于将`Quote`生成的表示`s`的双引号Go字符串文字附加到`dst`，并返回扩展缓冲区。 |
| `AppendQuoteRune`函数 | 此函数用于将`QuoteRune`生成的表示符文的单引号Go字符文字附加到`dst`，并返回扩展缓冲区。 |
| `AppendQuoteRuneToASCII`函数 | 此函数用于将`QuoteRuneToASCII`生成的表示符文的单引号Go字符文字附加到`dst`，并返回扩展缓冲区。 |
| `AppendQuoteRuneToGraphic`函数 | 此函数用于将`QuoteRuneToGraphic`生成的表示符文的单引号Go字符文字附加到`dst`，并返回扩展缓冲区。 |
| `AppendQuoteToASCII`函数 | 此函数用于将`QuoteToASCII`生成的表示`s`的带双引号的Go字符串文字附加到`dst`，并返回扩展缓冲区。 |
| `AppendQuoteToGraphic`函数 | 此函数用于将`QuoteToGraphic`生成的表示`s`的带双引号的Go字符串文字附加到`dst`，并返回扩展缓冲区。 |
| `AppendUint`函数 | 此函数用于将`FormatUint`生成的无符号整数`i`的字符串形式附加到`dst`，并返回扩展缓冲区。 |
| `Atoi`函数 | 此函数等效于`ParseInt(s, 10, 0)`，并转换为`int`类型。 |
| `CanBackquote`函数 | 此函数用于检查给定字符串是否可以原封不动地表示为不带制表符以外的控制字符的单行反引号字符串。 |
| `FormatBool`函数 | 此函数用于根据`x`的值返回`TRUE`或`FALSE`。 |
| `FormatFloat`函数 | 此函数用于根据格式`fmt`和精度`prec`将浮点数`f`转换为字符串。 |
| `FormatInt`函数 | 此函数用于返回在2<=`base`<=36进制下整数`i`的字符串表示形式。 |
| `FormatUint`函数 | 此函数用于返回在2<=`base`<=36进制下无符号整数`i`的字符串表示形式。 |
| `IsGraphic`函数 | 此函数用于检查符文是否由Unicode定义为图形。 |
| `IsPrint`函数 | 此函数用于检查符文是否定义为可通过Go打印，定义与`unicode.IsPrint`：字母、数字、标点符号、符号和ASCII空格。 |
| `Itoa`函数 | 此函数相当于`FormatInt(int64(i), 10)`。 |
| `ParseBool`函数 | 此函数用于返回字符串表示的布尔值。 |
| `ParseFloat`函数 | 此函数用于将字符串`s`转换为精度由`bitSize`指定的浮点数：32(对于`float32`)或64(对于`float64`)。 |
| `ParseInt`函数 | 此函数解释给定基数(0，2到36)和位大小(0到64)的字符串`s`，并返回相应的值`i`。 |
| `ParseUint`函数 | 此函数类似于`ParseInt`，但用于无符号数字。 |
| `Quote`函数 | 此函数用于返回表示`s`的双引号Go字符串文字。 |
| `QuoteRune`函数 | 此函数用于返回表示符文的单引号Go字符文字。 |
| `QuoteRuneToASCII`函数 | 此函数用于返回表示符文的单引号Go字符文字。 |
| `QuoteRuneToGraphic`函数 | 此函数用于返回表示符文的单引号Go字符文字。 |
| `QuoteToASCII`函数 | 此函数用于返回表示`s`的双引号Go字符串文字。 |
| `QuoteToGraphic`函数 | 此函数用于返回表示`s`的双引号Go字符串文字。 |
| `Unquote`函数 | 此函数将`s`解释为单引号、双引号或反引号Go字符串文字，返回`s`引号的字符串值。 |
| `UnquoteChar`函数 | 此函数用于解码转义字符串或字符串`s`表示的字符文字中的第一个字符或字节。 |

**示例1：**

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

输出：

```go
Rune : 'c'
```

**示例2：**

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

输出：

```go
int
244
```