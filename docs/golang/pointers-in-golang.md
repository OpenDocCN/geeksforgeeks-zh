# 戈朗的指针

> 原文:[https://www.geeksforgeeks.org/pointers-in-golang/](https://www.geeksforgeeks.org/pointers-in-golang/)

Go 编程语言或 [Golang](https://www.geeksforgeeks.org/go-programming-language-introduction/) 中的指针是一个变量，用于存储另一个变量的内存地址。Golang 中的指针也被称为特殊变量。[变量](https://www.geeksforgeeks.org/go-variables/)用于在系统的特定内存地址存储一些数据。内存地址总是以十六进制格式出现(从 0x 开始，如 0xFFAAF 等)。).

**指针的需求是什么？**

要理解这种需要，首先要理解变量的概念。变量是存储实际数据的内存位置的名称。要访问存储的数据，我们需要特定存储位置的地址。手动记住所有的内存地址(十六进制格式)是一种开销，这就是为什么我们使用变量来存储数据，变量只需使用它们的名称就可以访问。
Golang 还允许使用文字表达式将十六进制数保存到变量中，即从 **0x** 开始的数是十六进制数。

**示例:**在下面的程序中，我们将十六进制数存储到一个变量中。但是你可以看到值的类型是 *int* 并保存为十进制或者你可以说类型 *int* 的十进制值正在存储。但是解释这个例子的要点是，我们存储了一个十六进制值(将其视为内存地址)，但它不是指针，因为它不指向另一个变量的任何其他内存位置。它只是一个用户定义的变量。所以这就产生了对指针的需求。

## 去

```go
// Golang program to demonstrate the variables
// storing the hexadecimal values
package main

import "fmt"

func main() {

    // storing the hexadecimal
    // values in variables
    x := 0xFF
    y := 0x9C

    // Displaying the values
    fmt.Printf("Type of variable x is %T\n", x)
    fmt.Printf("Value of x in hexadecimal is %X\n", x)
    fmt.Printf("Value of x in decimal is %v\n", x)

    fmt.Printf("Type of variable y is %T\n", y)
    fmt.Printf("Value of y in hexadecimal is %X\n", y)
    fmt.Printf("Value of y in decimal is %v\n", y)   

}
```