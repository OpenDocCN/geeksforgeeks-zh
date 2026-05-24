# 使用命名返回值和默认值的 Golang 程序

> 原文:[https://www . geesforgeks . org/golang-使用命名返回值和默认值的程序/](https://www.geeksforgeeks.org/golang-program-that-uses-named-return-values-and-defaults/)

Golang 函数具有特殊的功能，允许它们为返回值提供名称。这些命名返回值可以用作参数或变量。命名的返回值也使用数据类型的默认值，如 int 类型的 0 等。为了理解这个概念，我们举个例子:

```go
// Golang Program that Uses Named
// Return Values and Defaults
package main

import "fmt"

// taking a function having named return
// values as dsa and placement
func courses(numbers []int) (dsa int, placement int) {

    // If the slice is at least two
    // elements set dsa and placement.
    // Else, leave the return values as zero.
    if len(numbers) >= 2 {
        dsa = numbers[0]
        placement = numbers[len(numbers)-1]
    }
    return dsa, placement
}

func main() {

    // For a zero-element
    // slice, these will return 0.
    fmt.Println("Displaying Default Values For Named Return Values")
    prices := []int{}
    fmt.Println(courses(prices))
    fmt.Println()

    fmt.Println("Displaying Assigned Values For Named Return Values")

    // The dsa and placement
    // values are set now
    prices = []int{2499, 7499}
    fmt.Println(courses(prices))
}
```

**例:**

```go
Displaying Default Values For Named Return Values
0 0

Displaying Assigned Values For Named Return Values
2499 7499

```