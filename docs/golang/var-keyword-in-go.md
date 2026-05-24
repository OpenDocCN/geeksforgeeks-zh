# GO

中的 var 关键字

> Original: [https://www.geeksforgeeks.org/var-keyword-in-go/](https://www.geeksforgeeks.org/var-keyword-in-go/)

**[Golang](https://www.geeksforgeeks.org/go-programming-language-introduction/)中的 var 关键字**用于创建具有适当名称和初始值的特定类型的[变量](https://www.geeksforgeeks.org/go-variables/)。 在使用*var*关键字声明变量时，初始化是可选的，我们将在本文后面讨论该关键字。

**语法：**

```go
var identifier type = expression
```

**示例：**

```go
// here geek1 is the identifier 
// or variable name, int is the
// type and 200 is assigned value
var geek1 int = 200

```

正如您所知道的，Go 是一种静态类型的语言，但是它仍然提供了一种在声明变量时删除数据类型声明的功能，如下面的语法所示。 这通常被称为**类型推理**。

**语法：**

```go
var identifier = initialValue
```

**示例：**

```go
var geek1 = 200

```

#### 使用 var 关键字的多个变量声明

Var 关键字还用于在一行中声明多个变量。 您还可以为变量提供初始值，如下所示：

*   使用 var 关键字和类型声明多个变量：

    ```go
    var geek1, geek2, geek3, geek4 int
    ```

*   使用 var 关键字以及类型和初始值声明多个变量：

    ```go
    var geek1, geek2, geek3, geek4 int = 10, 20, 30, 40
    ```

**注：**

*   You can also use **type inference(discussed above)** that will let the compiler to know about the type i.e. there is an option to remove the type while declaring multiple variables.

    *示例：*

    ```go
    var geek1, geek2, geek3, geek4 = 10, 20, 30.30, true
    ```

*   You can also use multiple lines to declare and initialize the values of different types using a var keyword as follows:

    *示例：*

    ```go
    var(
         geek1 = 100
         geek2 = 200.57
         geek3 bool
         geek4 string = "GeeksforGeeks"
    )

    ```

*   While using type during declaration you are only allowed to declare multiple variables of the same type. But removing type during declarations you are allowed to declare multiple variables of different types.

    *示例：*

    ```go
    // Go program to demonstrate the multiple 
    // variable declarations using var keyword
    package main

    import "fmt"

    func main() {

        // Multiple variables of the same type
        // are declared and initialized
        // in the single line along with type
        var geek1, geek2, geek3 int = 232, 784, 854

        // Multiple variables of different type
        // are declared and initialized
        // in the single line without specifying
        // any type
        var geek4, geek5, geek6 = 100, "GFG", 7896.46

       // Display the values of the variables
       fmt.Printf("The value of geek1 is : %d\n", geek1)

       fmt.Printf("The value of geek2 is : %d\n", geek2)

       fmt.Printf("The value of geek3 is : %d\n", geek3)

       fmt.Printf("The value of geek4 is : %d\n", geek4)

       fmt.Printf("The value of geek5 is : %s\n", geek5)

       fmt.Printf("The value of geek6 is : %f", geek6)

    }
    ```

    发帖主题：Re：Колибри0.7.0

    ```go
    The value of geek1 is : 232
    The value of geek2 is : 784
    The value of geek3 is : 854
    The value of geek4 is : 100
    The value of geek5 is : GFG
    The value of geek6 is : 7896.460000

    ```

**var 关键字要点：**

*   在使用 var 关键字声明变量期间，您可以删除 type 或=表达式，但不能同时删除两者。 如果您要这样做，那么编译器将给出一个错误。
*   If you removed the expression then the variable will contain the zero-value for numbers and *false* for booleans *“”* for strings and nil for interface and reference type by default. So, there is no such concept of an uninitialized variable in Go language.

    **示例：**

    ```go
    // Go program to illustrate
    // concept of var keyword
    package main

    import "fmt"

    func main() {

        // Variable declared but
        // no initialization
        var geek1 int
        var geek2 string
        var geek3 float64
        var geek4 bool

        // Display the zero-value of the variables
        fmt.Printf("The value of geek1 is : %d\n", geek1)

        fmt.Printf("The value of geek2 is : %s\n", geek2)

        fmt.Printf("The value of geek3 is : %f\n", geek3)

        fmt.Printf("The value of geek4 is : %t", geek4)

    }
    ```

    发帖主题：Re：Колибри0.7.0

    ```go
    The value of geek1 is : 0
    The value of geek2 is : 
    The value of geek3 is : 0.000000
    The value of geek4 is : false

    ```