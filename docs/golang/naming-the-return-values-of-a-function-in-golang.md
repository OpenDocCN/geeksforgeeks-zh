# 在 Golang 中命名函数的返回值

> 原文:[https://www . geeksforgeeks . org/golang 中函数返回值的命名/](https://www.geeksforgeeks.org/naming-the-return-values-of-a-function-in-golang/)

返回值有助于在执行其主体中给出的指令后保留[函数](https://www.geeksforgeeks.org/functions-in-go-language/)的最终输出。Golang 中的函数在返回值方面表现出多样性，并依赖程序员来决定是否命名它们。
Golang 引入了“*裸返回*”的概念，允许使用 Return 关键字，而无需在函数体中明确说明返回值，前提是返回值在函数头中声明。但是，变量名必须与函数头中定义的相同。

```go
package main

import "fmt"

// This function returns a string message by taking a parameter
// "name" of string type. The Naked return concept is being
// displayed here since the return statement not specify the return
// of message variable. The returning of the message variable
// has already being defined 
func greeting(name string) (message string) {

    // Since the variable is already 
    // defined in function variable
    // there is no need to declare it 
    // again in the function body
    // using " := " operator.

    // The name "message" must be same as 
    // the one declared in the function header.
    message = "Hello, " + name

    // This statement returns message variable
    // without explicitly stating its name
    return 
}

// Driver code
func main() {

    // The return value of greeting 
    // function is stored in msg variable
    msg := greeting("GFG")

    // Printing output
    fmt.Println(msg) 
}
```

**输出:**

```go
Hello, GFG

```

此外，函数可以返回一个变量，而无需在函数头中指定其名称，只需指定其数据类型。

```go
package main

import "fmt"

// This function returns a string datatype
// Since the return variable is not 
// defined in the function header,
// There is an explicit need to specify
// the variable to return

func greeting(name string) string {
    message := "Hello, " + name
    return message
}

// Driver code
func main() {
    msg := greeting("GFG")
    fmt.Println(msg)
}
```

**输出:**

```go
Hello, GFG

```

一个函数也可以返回多个值并接收多个参数。但是，要使用返回多个值的函数，函数返回的变量数必须等于函数执行完成时保存返回值的变量数。

```go
package main

import "fmt"

// The below function returns four
// variables after performing operations
// on the two parameters that were passed to it

func operations(a, b int) (sum, diff, prod, div int) {

    // The four variables to be returned are defined here

    sum, diff, prod, div = a+b, a-b, a*b, a/b

    // returning the above-defined four variables.
    return
}

// Driver code
func main() {
    a, b := 5, 3

    // Since the function returns four values,
    // Four receiver variables must be used.
    sum, diff, prod, div := operations(a, b)
    fmt.Println(sum, diff, prod, div)
}
```

**输出:**

```go
8 2 15 1

```