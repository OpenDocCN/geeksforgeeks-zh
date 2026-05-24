# Golang 中 var 关键字和短申报运算符的区别

> 原文:[https://www . geesforgeks . org/var-keyword-and-short-declaration-operator-in-golang/](https://www.geeksforgeeks.org/difference-between-var-keyword-and-short-declaration-operator-in-golang/)

一个[变量](https://www.geeksforgeeks.org/go-variables/)是一个用于保存数值的存储位置或占位符。它允许我们操作和检索存储的信息。有两种方法可以声明戈兰的变量，如下所示:

*   **使用 var 关键字***   **Using a short declaration operator (*:=*)

    #### var 关键字和短声明运算符之间的区别

    | 做个关键词 | 简短声明运算符 |
    | var 是一个出现在 Golang 的**词汇关键词**。 | **:=** 被称为短声明运算符。 |
    | 它用于声明和初始化函数内外的变量。 | 它仅用于声明和初始化函数内部的变量。 |
    | 利用这一点，变量通常具有包级或全局级范围。它也可以有局部范围。 | 这里，变量只有局部作用域，因为它们只在函数内部声明。 |
    | 变量的声明和初始化可以分别进行。 | 变量的声明和初始化必须同时进行。 |
    | 将类型与变量声明放在一起是可选的。 | 没必要放铅字。如果你，它会给出错误。 |

    **例 1:** 在这个程序中可以看到 *myvariable1* 是用 *var* 关键字声明的，它有局部范围。 *myvariable2* 也是使用 var 关键字和 type int 声明的，但是没有初始化。因此它将采用 int 类型的默认值，即零(您可以在输出中看到)。 *myvariable3* 是使用短变量声明运算符声明和初始化的，它有局部作用域。

    ```go
    // Go program to show the use of var lexical 
    // keyword and short declaration operator
    package main

    import (
        "fmt"
    )

    func main() {

    // using var keyword to declare 
    // and initialize the variable
    var myvariable1 = 100

    fmt.Println(myvariable1)

    // using var keyword to declare 
    // the variable along with type
    var myvariable2 int

    fmt.Println(myvariable2)

    // using short variable declaration
    myvariable3 := 200

    fmt.Println(myvariable3)

    }
    ```

    **输出:**

    ```go
    100
    0
    200

    ```

    **例 2:** 在这个程序中可以看到 *myvariable1* 是用 *var* 关键字声明的，它有*全局范围*。 *myvariable2* 也是使用 var 关键字和 type int 一起声明的，但是没有进行初始化。因此它将采用 int 类型的默认值，即零(您可以在输出中看到)。 *myvariable3* 使用短变量声明运算符进行声明和初始化，具有局部作用域。

    ```go
    // Go program to show the use of var lexical 
    // keyword and short declaration operator
    package main

    import (
        "fmt"
    )

    // using var keyword to declare 
    // and initialize the variable
    // it is package or you can say 
    // global level scope
    var myvariable1 = 100

    func main() {

    // accessing myvariable1 inside the function
    fmt.Println(myvariable1)

    // using var keyword to declare 
    // the variable along with type
    var myvariable2 int

    fmt.Println(myvariable2)

    // using short variable declaration
    myvariable3 := 200

    fmt.Println(myvariable3)

    }
    ```

    **输出:**

    ```go
    100
    0
    200

    ```

    **例 3:** 在这个程序中可以看到 *myvariable1* 是用 *var* 关键字声明的，它有*全局范围*。 *myvariable2* 也是使用 var 关键字和 type int 一起声明的，但是没有进行初始化。因此它将采用 int 类型的默认值，即零(您可以在输出中看到)。 *myvariable3* 是使用函数外的短变量声明运算符声明和初始化的，这是不允许的，因此会产生错误。

    ```go
    // Go program to show the use of var lexical 
    // keyword and short declaration operator
    package main

    import (
        "fmt"
    )

    // using var keyword to declare 
    // and initialize the variable
    // it is package or you can say 
    // global level scope
    var myvariable1 = 100

    // using short variable declaration
    // it will give an error as it is not 
    // allowed outside the function
    myvariable3 := 200

    func main() {

    // accessing myvariable1 inside the function
    fmt.Println(myvariable1)

    // using var keyword to declare 
    // the variable along with type
    var myvariable2 int

    fmt.Println(myvariable2)

    fmt.Println(myvariable3)

    }
    ```

    **错误:**

    > 。/prog.go:18:1:语法错误:函数体外部的非声明语句**