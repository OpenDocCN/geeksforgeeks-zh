# Golang 字符串中反斜杠怎么写？

> 原文:[https://www . geesforgeks . org/golang-string 中的反斜线书写方式/](https://www.geeksforgeeks.org/how-to-write-backslash-in-golang-string/)

在大多数编程语言中，反斜杠(\)用作转义序列字符，Golang 也是如此。因此，如果用户需要在字符串中写反斜杠，他可以使用这两种常见的方法。

**1。**用户可以在他/她想要显示的反斜杠(\)前使用另一个反斜杠。

**例:**

```go
// Printing backslash in Golang string
package main

import "fmt"

func main() {

    // using another backslash
    fmt.Println("\\Hello, Welcome to GeeksforGeeks")
}
```

**输出:**

```go
\Hello, Welcome to GeeksforGeeks
```

**说明:**假设用户想在字符串的开头写反斜杠。这是通过在所需的反斜杠前使用转义符“\”来完成的，如上面的示例所示。通过这种方式，用户可以在字符串中的任意位置插入反斜杠。

**2。**另一种方法是使用原始字符串(`)。

```go
// Printing backslash in Golang string
package main

import "fmt"

func main() {

    // using raw string lateral (`)
    fmt.Println(`\Happy Learning\`)
}
```

**输出:**

```go
\Happy Learning\
```

**解释:**在这个例子中，我们使用了一个原始的字符串横向(`)在字符串中写了一个反斜杠。如果用户想要在反斜杠之间写入一个字符串，他可以通过在原始字符串文字(`)中写入所需的字符串来实现，如本例所示。