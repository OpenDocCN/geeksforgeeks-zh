# 推迟 Golang 中的关键字

> 原文:[https://www.geeksforgeeks.org/defer-keyword-in-golang/](https://www.geeksforgeeks.org/defer-keyword-in-golang/)

在 Go 语言中，延迟语句延迟[函数](https://www.geeksforgeeks.org/functions-in-go-language/)或方法或[匿名方法](https://www.geeksforgeeks.org/anonymous-function-in-go-language/)的执行，直到附近的函数返回。换句话说，延迟函数或方法调用参数会立即求值，但它们不会执行，直到附近的函数返回。您可以使用 defer 关键字创建延迟方法、函数或匿名函数。

**语法:**

```go
// Function
defer func func_name(parameter_list Type)return_type{
// Code
}

// Method
defer func (receiver Type) method_name(parameter_list){
// Code
}

defer func (parameter_list)(return_type){
// code
}()
```

**要点:**

*   In Go language, multiple defer statements are allowed in the same program, and they are executed in LIFO (last in first out) order, as shown in Example 2.
*   In a delay statement, parameters are calculated when the delay statement is executed, not when the call is made.
*   The delay statement is generally used to ensure that the file is closed at the end of the demand, or to close the channel, or to catch the panic in the program.

让我们借助一个例子来讨论这个概念:

**例 1:**

## 去

```go
// Go program to illustrate the
// concept of the defer statement
package main

import "fmt"

// Functions
func mul(a1, a2 int) int {

    res := a1 * a2
    fmt.Println("Result: ", res)
    return 0
}

func show() {
    fmt.Println("Hello!, GeeksforGeeks")
}

// Main function
func main() {

    // Calling mul() function
    // Here mul function behaves
    // like a normal function
    mul(23, 45)

    // Calling mul()function
    // Using defer keyword
    // Here the mul() function
    // is defer function
    defer mul(23, 56)

    // Calling show() function
    show()
}
```

**输出:**

```go
Result:  1035
Hello!, GeeksforGeeks
Result:  1288
```

**说明:**在上面的例子中，我们有两个名为 *mul()* 和 *show()* 的函数。其中 *show()* 函数在 *main()* 函数中正常调用， *mul()* 函数有两种不同的调用方式:

*   First, we call the *mul* function normally (without the defer keyword), that is, mul (23,45), which is executed when the function is called (output: result: 1035).
*   Secondly, we use the delay keyword to call *mul ()* function as the delay function, that is, delay *mul (23,56)* and execute it when all the surrounding methods return (output: result: 1288).

**例 2:**

## Go

```go
// Go program to illustrate
// multiple defer statements, to illustrate LIFO policy
package main

import "fmt"

// Functions
func add(a1, a2 int) int {
    res := a1 + a2
    fmt.Println("Result: ", res)
    return 0
}

// Main function
func main() {

    fmt.Println("Start")

    // Multiple defer statements
    // Executes in LIFO order
    defer fmt.Println("End")
    defer add(34, 56)
    defer add(10, 10)
}
```

**输出:**

```go
Start
Result:  20
Result:  90
End
```