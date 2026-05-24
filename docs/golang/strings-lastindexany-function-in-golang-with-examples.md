# Golang 中的 Strings.LastIndexAny()函数，示例为

> Original: [https://www.geeksforgeeks.org/strings-lastindexany-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-lastindexany-function-in-golang-with-examples/)

**Golang 中的 LastIndexAny()函数**用于从给定字符串中的字符中查找任何 Unicode 代码点的最后一个实例的索引。 如果未找到字符的 Unicode 代码点，则返回-1。 因此，此函数返回整数值。 以零作为字符串的起始索引来计算索引。

**语法：**

```go
func LastIndexAny(str, chars string) int
```

这里，str 是原始字符串，charstr 是我们要查找其最后索引值的字符的 Unicode 代码点。

**示例 1：**

```go
// Golang program to illustrate the
// strings.LastIndexAny() Function
package main

import (
    "fmt"
    "strings"
)

func main() {

    // taking a string
    str := "GeeksforGeeks"

    // using the function
    fmt.Println(strings.LastIndexAny(str, "Ge"))
    fmt.Println(strings.LastIndexAny(str, "g"))
    fmt.Println(strings.LastIndexAny(str, "sf"))
}
```

发帖主题：Re：Колибри0.7.0

```go
10
-1
12

```

对于第二个输出，字符‘g’不存在，因此结果显示-1。 请注意，此函数区分大小写，因此它采用不同的‘g’和‘g’。

**示例 2：**

```go
// Golang program to illustrate the
// strings.LastIndexAny() Function
package main

import (
    "fmt"
    "strings"
)

func main() {

    // taking a string
    str := "New Delhi, India"

    // using the function
    fmt.Println(strings.LastIndexAny(str, "Ii"))
    fmt.Println(strings.LastIndexAny(str, " "))
}
```

发帖主题：Re：Колибри0.7.8.0

对于第一个输出，字符是‘i’和‘i’。 因此，编译器将显示‘i’或‘i’最后一次出现的索引，因为‘i’在这里最后出现，所以这将是输出。 对于第二个输出，要搜索的字符是空格。 由于给定字符串中有两个空格，因此输出将是最后一个空格的索引。