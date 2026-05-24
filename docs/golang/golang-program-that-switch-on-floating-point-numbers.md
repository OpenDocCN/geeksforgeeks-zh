# 开启浮点数的 Golang 程序

> 原文:[https://www . geesforgeks . org/golang-program-on-switch-on-floating-numbers/](https://www.geeksforgeeks.org/golang-program-that-switch-on-floating-point-numbers/)

借助[开关盒](https://www.geeksforgeeks.org/switch-statement-in-go/)我们可以实现尽可能多的 if 语句的功能。在 Golang 中，开关案例可以处理字符串、变量列表，包括整数值和浮点值。

**语法:**

> switch optstatementopt expression {
> case expression 1:语句..
> 案例表述 2:陈述..
> ……
> 默认:声明..

**例 1:** 在这个例子中，我们可以看到，通过使用开关情况，并假设变量为浮动类型，我们可以利用开关情况。一些编程语言不允许我们使用浮点值，但是 Golang 允许我们使用。

```go
// Golang Program that switch
// on floating-point numbers
package main

// Here "fmt" is formatted IO which
// is same as C’s printf and scanf.
import "fmt"

// Main function
func main() {
    val := 1.1

    // Use switch on the day variable.
    switch {
    case val == 1.2:
        fmt.Println("One Point Two")
    case val == 1.3:
        fmt.Println("One Point Three")
    case val == 1.1:
        fmt.Println("One Point One")
    }
}
```

**输出:**

```go
One Point One

```

**例 2:**

```go
// Golang Program that switch
// on floating-point numbers
package main

// Here "fmt" is formatted IO which
// is same as C’s printf and scanf.
import "fmt"

// Main function
func main() {
    gfg := 4.5

    // Use switch on the day variable.
    switch {
    case gfg == 1.2:
        fmt.Println("Geek")
    case gfg == 4.5:
        fmt.Println("For")
    case gfg == 5.5:
        fmt.Println("Geeks")
    }
}
```

**输出:**

```go
For

```