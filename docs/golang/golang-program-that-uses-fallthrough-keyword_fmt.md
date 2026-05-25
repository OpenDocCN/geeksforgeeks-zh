# 使用 fallthrough 关键字的 Golang 程序

> 原文：[https://www.geeksforgeeks.org/golang-program-that-uses-fallthrough-keyword/](https://www.geeksforgeeks.org/golang-program-that-uses-fallthrough-keyword/)

借助`fallthrough`语句，即使表达式不匹配，我们也可以在`switch`情况下，在语句刚执行完之后使用来转移程序控制。通常情况下，匹配后的第一行刚执行完，控制就会从`switch`语句中出来。不要把`fallthrough`放在`switch` `case`的最后一个语句中。

## 示例 1

在本例中，我们可以看到，通过使用带有`fallthrough`的`switch` `case`，并假设变量为字符串类型，我们可以使用`switch` `case`。

```go
// Golang program to show the
// uses of fallthrough keyword
package main

// Here "fmt" is formatted IO which
// is same as C’s printf and scanf.
import "fmt"

// Main function
func main() {
    day := "Tue"

    // Use switch on the day variable.
    switch {
    case day == "Mon":
        fmt.Println("Monday")
        fallthrough
    case day == "Tue":
        fmt.Println("Tuesday")
        fallthrough
    case day == "Wed":
        fmt.Println("Wednesday")
    }
}
```

**输出：**

```go
Tuesday
Wednesday
```

## 示例 2

```go
// Golang program to show the
// uses of fallthrough keyword
package main

// Here "fmt" is formatted IO which
// is same as C’s printf and scanf.
import "fmt"

// Main function
func main() {
    gfg := "Geek"

    // Use switch on the day variable.
    switch {
    case gfg == "Geek":
        fmt.Println("Geek")
        fallthrough
    case gfg == "For":
        fmt.Println("For")
        fallthrough
    case gfg == "Geeks":
        fmt.Println("Geeks")
    }
}
```

**输出：**

```go
Geek
For
Geeks
```