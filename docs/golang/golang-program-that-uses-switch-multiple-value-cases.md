# 使用开关的 Golang 程序，多值情况

> 原文:[https://www . geesforgeks . org/golang-program-the-use-switch-multi-value-cases/](https://www.geeksforgeeks.org/golang-program-that-uses-switch-multiple-value-cases/)

Switch 语句是一个多路分支，它提供了一种过长的 if-else 比较的替代方法。它根据表达式的值或单个变量的状态，从多个块的列表中选择要执行的单个块。使用多值情况的 switch 语句对应于在单个情况下使用多个值的**。**这是通过用逗号分隔案例中的多个值来实现的。

**例 1:**

```go
// Golang program to illustrate the
// use of switch with multiple value cases
package main

import (
    "fmt"
)

func main() {

    // string to input month from user
    var month string
    fmt.Scanln(&month)

    // switch case for predicting
    // seasons for month entered

    // each switch case has more 
    // than one values
    switch month {
        case "january", "december":
            fmt.Println("Winter.")
        case "february", "march":
            fmt.Println("Spring.")
        case "april", "may", "june":
            fmt.Println("Summer.")
        case "july", "august":
            fmt.Println("Monsoon.")
        case "september", "november":
            fmt.Println("Autumn.")
    }
}
```

```go
Input : january
Output : Winter.

Input : september
Output : Autumn.

```

我们不是在同一个季节的几个月里制作不同的单个案例，而是在不同的月份制作相同的产品。这就节省了我们编写冗余代码的时间。

**例 2:**

```go
// Golang program to illustrate the
// use of switch with multiple value cases
package main

import (
    "fmt"
)

func main() {

    // integer to input number from 
    // user (only 1-10)
    var number int
    fmt.Scanln(&number)

    // switch case for predicting
    // whether the number is even or odd

    // each switch case has more 
    // than one values
    switch number {
        case 2, 4, 6, 8, 10:
            fmt.Println("You entered an even number.")
        case 1, 3, 5, 7, 9:
                fmt.Println("You entered an odd number.")
    }
}
```

```go
Input : 6
Output : You entered an even number.

Input : 5
Output : You entered an odd number.

```

我们不需要写 10 个不同的案例来检查输入的数字是否为偶数，我们可以简单地使用多个案例值在两个开关案例中做同样的事情。

**例 3:**

```go
// Golang program to illustrate the
// use of switch with multiple value cases
package main

import (
    "fmt"
)

func main() {

    // character input (a-z or A-Z)
    var alphabet string
    fmt.Scanln(&alphabet)

    // switch case for predicting
    // whether the character is
    // uppercase or lowercase

    // each switch case has more 
    // than one values
    switch alphabet {
        case "a", "b", "c", "d", "e", "f", "g", "h", "i",
        "j", "k", "l", "m", "n", "o", "p", "q", "r", "s", "t",
        "u", "v", "w", "x", "y", "z":
            fmt.Println("Lowercase alphabet character.")

        case "A", "B", "C", "D", "E", "F", "G", "H", "I", "J",
        "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T",
        "U", "V", "W", "X", "Y", "Z":
            fmt.Println("Uppercase alphabet character.")
    }
}
```

```go
Input : g
Output : Lowercase alphabet character.

Input : F
Output : Uppercase alphabet character.

```