# 如何在 Golang 中声明和访问指针变量？

> 原文:[https://www . geesforgeks . org/如何声明和访问指针变量 in-golang/](https://www.geeksforgeeks.org/how-to-declare-and-access-pointer-variable-in-golang/)

[指针](https://www.geeksforgeeks.org/pointers-in-golang/)在 Go 编程语言或 [Golang 中](https://www.geeksforgeeks.org/golang-tutorial-learn-go-programming-language/)是一个变量，用于存储另一个变量的内存地址。Golang 中的指针也被称为特殊变量。变量用于在系统的特定内存地址存储一些数据。内存地址总是以十六进制格式出现(从 0x 开始，如 0xFFAAF 等)。).

在开始之前，我们将在指针中使用两个重要的运算符，即

***运算符**也称为解引用运算符，用于声明指针变量和访问存储在地址中的值。

**&运算符**被称为地址运算符，用于返回变量的地址或访问指向指针的变量的地址。

***声明指针*** :

```go
var pointer_name *Data_Type
```

*示例:*下面是字符串类型的指针，只能存储*字符串*变量的内存地址。

```go
var s *string
```

***指针初始化:*** 为此，您需要使用地址操作符用另一个变量的内存地址初始化指针，如下例所示:

```go
// normal variable declaration
var a = 45

// Initialization of pointer s with 
// memory address of variable a
var s *int = &a

```

**示例:**在下面的示例中，使用指针，我们将访问地址存储在指针中的变量的值。

```go
// Golang program to show how to declare
// and access pointer variable in Golang
package main

import (
    "fmt"
)

func main() {

    // variable declaration
    var dummyVar string = "Geeks For Geeks"

    // pointer declaration
    var pointerVariable *string

    // assigning variable address to pointer variable
    pointerVariable = &dummyVar

    // Prints the address of the dummyVar variable
    fmt.Printf("\nAddress of the variable: %v", &dummyVar)

    // Prints the address stored in pointer
    fmt.Printf("\nAddress stored in the pointer variable: %v", pointerVariable)

    // Value of variable
    fmt.Printf("\nValue of the Actual Variable: %s", dummyVar)

    // Value of variable whose address is stored in pointer
    fmt.Printf("\nValue of the Pointer variable: %s", *pointerVariable)
}
```

**输出:**

```go
Address of the variable: 0xc00010a040
Address stored in the pointer variable: 0xc00010a040
Value of the Actual Variable: Geeks For Geeks
Value of the Pointer variable: Geeks For Geeks

```

**说明:**这里(&)符号是用来获取存储值的变量的地址为“极客为极客”。该变量拥有的地址与指针中存储的地址相同。因此& dummyVar 和 pointerVariable 的输出是一样的。要访问存储在地址中的值，该值存储在指针中，我们使用(*)符号。