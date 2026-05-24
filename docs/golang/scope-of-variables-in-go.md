# Go 中变量的范围

> 原文:[https://www.geeksforgeeks.org/scope-of-variables-in-go/](https://www.geeksforgeeks.org/scope-of-variables-in-go/)

#### 先决条件:[Go 编程语言中的变量](https://www.geeksforgeeks.org/go-variables/)

变量的作用域可以定义为程序中可访问特定变量的部分。变量可以在类、方法、循环等中定义。像 [C](https://www.geeksforgeeks.org/c-programming-language/) / [C++](https://www.geeksforgeeks.org/c-plus-plus/) 一样，在 Golang 中，所有标识符都是词汇(或静态)范围的，即变量的范围可以在编译时确定。或者你可以说一个变量只能从定义它的代码块中调用。

变量的 Golang 作用域规则可以分为两类，这取决于变量的声明位置:

*   **局部变量**(在块或函数中声明)
*   **全局变量**(在块或函数外声明)

## 局部变量

*   在函数或块中声明的变量称为局部变量。这些在功能或块之外是不可访问的。
*   这些变量也可以在 for、while 语句等中声明。函数内部。
*   然而，这些变量可以被函数内部的嵌套代码块访问。
*   这些变量也被称为块变量。
*   如果这些变量在同一个作用域中用相同的名称声明两次，将会出现编译时错误。
*   这些变量在函数执行结束后不存在。
*   在循环外部声明的变量也可以在嵌套循环中访问。这意味着方法和所有循环都可以访问全局变量。局部变量可由该函数内部的循环和函数访问。
*   在循环体内部声明的变量对于循环体外部是不可见的。

**示例:**

```go
// Go program to illustrate the
// local variables
package main 

import "fmt"

// main function
func main() { // from here local level scope of main function starts 

 // local variables inside the main function
 var myvariable1, myvariable2 int = 89, 45

// Display the values of the variables 
fmt.Printf("The value of myvariable1 is : %d\n", 
                                    myvariable1) 

fmt.Printf("The value of myvariable2 is : %d\n", 
                                    myvariable2) 

} // here local level scope of main function ends
```

**输出:**

```go
The value of myvariable1 is : 89
The value of myvariable2 is : 45

```

## 全局变量

*   在函数或块之外定义的变量称为全局变量。
*   这些在程序的整个生命周期中都是可用的。
*   这些在所有函数或块之外的程序顶部声明。
*   这些可以从程序的任何部分访问。

**示例:**

```go
// Go program to illustrate the
// global variables
package main 

import "fmt"

// global variable declaration
var myvariable1 int = 100

func main() { // from here local level scope starts 

// local variables inside the main function
var myvariable2 int = 200

// Display the value of global variable
fmt.Printf("The value of Global myvariable1 is : %d\n", 
                          myvariable1) 

// Display the value of local variable
fmt.Printf("The value of Local myvariable2 is : %d\n", 
                          myvariable2) 

// calling the function            
display()

} // here local level scope ends

// taking a function
func display() { // local level starts 

// Display the value of global variable
fmt.Printf("The value of Global myvariable1 is : %d\n", 
                          myvariable1) 

} // local scope ends here
```

**输出:**

```go
The value of Global myvariable1 is : 100
The value of Local myvariable2 is : 200
The value of Global myvariable1 is : 100

```

**注意:**如果函数内部存在一个与全局变量同名的局部变量，会发生什么？

答案很简单，即编译器会优先考虑局部变量。通常，当定义两个同名变量时，编译器会产生编译时错误。但是如果变量被定义在不同的范围内，那么编译器允许。只要定义了与全局变量同名的局部变量，编译器就会优先考虑局部变量。

*   **Example:** In the below program, you can clearly see the output. As myvariable1 value is 200 which is giving in function main. So you can say a local variable has a high preference over a global variable.

    ```go
    // Go program to show compiler giving preference
    // to a local variable over a global variable
    package main 

    import "fmt"

    // global variable declaration
    var myvariable1 int = 100

    func main() { // from here local level scope starts 

    // local variables inside the main function
    // it is same as global variable
    var myvariable1 int = 200

    // Display the value 
    fmt.Printf("The value of myvariable1 is : %d\n", 
                        myvariable1) 

    } // here local level scope ends
    ```

    **输出:**

    ```go
    The value of myvariable1 is : 200

    ```