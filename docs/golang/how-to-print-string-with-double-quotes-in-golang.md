# 如何在 Golang 中打印带双引号的字符串？

> 原文:[https://www . geesforgeks . org/如何打印带双引号的字符串-in-golang/](https://www.geeksforgeeks.org/how-to-print-string-with-double-quotes-in-golang/)

每当用户想要对一个字符串进行双引号时，他不能简单地将该字符串写在 *fmt 内的双引号内。Printf()命令*。这将只打印那些引号内的文本。要打印字符串和引号，他可以使用各种方法，包括某些转义字符。在 Golang 中有不同的方法来打印带双引号的字符串。

**1)使用%q 引用字符串:**

*句法:*

```go
fmt.Printf("%q", output)
```

```go
package main

import "fmt"

func main() {
    var result = "Welcome to GeeksforGeeks."
    fmt.Printf("%q", result)
}
```

*输出:*

```go
"Welcome to GeeksforGeeks."
```

*解释:*在上面的例子中，我们使用了“%q”来用双引号显示我们的字符串。

**2)使用转义字符“\”引用字符串:**

*句法:*

```go
fmt.Println("\"string\"")
```

```go
package main

import "fmt"

func main() {
    fmt.Println("\"GeeksforGeeks is a computer science portal\"")
}
```

*输出:*

```go
"GeeksforGeeks is a computer science portal"
```

*说明:*在上面的例子中，我们使用了一个转义字符“\”来打印一个带双引号的字符串。我们只需在双引号前添加一个反斜杠(\)即可。

**3)使用原始字符串横向(`)重复引用字符串:**

*句法:*

```go
fmt.Println(`"string\"`)
```

```go
package main

import "fmt"

func main() {
    fmt.Println(`"GeeksforGeeks"`)
}
```

*输出:*

```go
"GeeksforGeeks"
```

*说明:*在上面的例子中，我们使用了一个 raw string side(`)来打印一个带双引号的字符串。