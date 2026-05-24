# 使用字符串开关的 Golang 程序

> 原文:[https://www . geeksforgeeks . org/golang-program-the-use-string-switch/](https://www.geeksforgeeks.org/golang-program-that-uses-string-switch/)

借助[开关盒](https://www.geeksforgeeks.org/switch-statement-in-go/)我们可以实现尽可能多的 if 语句的功能。在 Golang 中，开关案例可以处理字符串、变量列表，包括整数值和浮点值。

**语法:**

> switch optstatementopt expression {
> case expression 1:语句..
> 案例表述 2:陈述..
> ……
> 默认:声明..

**示例 1:** 在这个示例中，我们可以看到，通过使用开关情况并假设变量为字符串类型，我们可以使用开关情况。

```go
// Golang program that uses string switch
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
    case day == "Tue":
        fmt.Println("Tuesday")
    case day == "Wed":
        fmt.Println("Wednesday")
    }
}
```

**输出:**

```go
Tuesday

```

**例 2:**

```go
// Golang program that uses string switch
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
    case gfg == "For":
        fmt.Println("For")
    case gfg == "Geeks":
        fmt.Println("Geeks")
    }
}
```

**输出:**

```go
Geek

```