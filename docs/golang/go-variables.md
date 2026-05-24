# Go 变量

> 原文:[https://www.geeksforgeeks.org/go-variables/](https://www.geeksforgeeks.org/go-variables/)

典型的程序使用各种值，这些值在执行过程中可能会改变。*例如*，对用户输入的值进行一些操作的程序。一个用户输入的值可能与另一个用户输入的值不同。因此，这使得有必要使用变量，因为另一个用户可能不会使用相同的值。当用户输入一个将在操作过程中使用的新值时，可以将其临时存储在计算机的随机存取存储器中，并且在整个执行过程中，这部分存储器中的这些值会发生变化，因此出现了另一个术语，称为**。因此，基本上，变量是可以在运行时更改的信息的占位符。和变量允许检索和操作存储的信息。**

****变量命名规则:****

*   **变量名必须以字母或下划线(_)开头。并且名称可以包含字母“a-z”或“A-Z”或数字 0-9 以及字符“_”。

    ```go
    Geeks, geeks, _geeks23  // valid variable
    123Geeks, 23geeks      // invalid variable

    ```** 
*   **变量名不应以数字开头。

    ```go
    234geeks  // illegal variable 
    ```** 
*   **变量的名称区分大小写。

    ```go
    geeks and Geeks are two different variables
    ```** 
*   **关键字不允许用作变量名。**
*   **变量名称的长度没有限制，但建议仅使用 4-15 个字母的最佳长度。**

#### **声明变量**

***在 Go 语言中，变量以两种不同的方式创建:***

1.  ****Using var keyword:** In Go language, variables are created using *var* keyword of a particular type, connected with name and provide its initial value.

    **语法:**

    ```go
    var variable_name type = expression
    ```

    **要点:**

    *   在上面的语法中，要么*类型*要么 *=* 表达式可以移除，但不是两者都可以，可以在变量的声明中移除。
    *   If the type is removed, then the type of the variable is determined by the value-initialize in the expression.

        **示例:**

        ```go
        // Go program to illustrate 
        // concept of variable
        package main

        import "fmt"

        func main() {

        // Variable declared and 
        // initialized without the 
        // explicit type
        var myvariable1 = 20
        var myvariable2 = "GeeksforGeeks"
        var myvariable3 = 34.80

        // Display the value and the
        // type of the variables
        fmt.Printf("The value of myvariable1 is : %d\n",
                                          myvariable1)

        fmt.Printf("The type of myvariable1 is : %T\n",
                                          myvariable1)

        fmt.Printf("The value of myvariable2 is : %s\n",
                                              myvariable2)

        fmt.Printf("The type of myvariable2 is : %T\n",
                                          myvariable2)

        fmt.Printf("The value of myvariable3 is : %f\n",
                                              myvariable3)

        fmt.Printf("The type of myvariable3 is : %T\n",
                                          myvariable3)

        }
        ```

        **输出:**

        ```go
        The value of myvariable1 is : 20
        The type of myvariable1 is : int
        The value of myvariable2 is : GeeksforGeeks
        The type of myvariable2 is : string
        The value of myvariable3 is : 34.800000
        The type of myvariable3 is : float64

        ```

    *   If the expression is removed, then the variable holds zero-value for the type like zero for the number, false for Booleans, **“”** for strings, and nil for interface and reference type. So, there is ***no such concept of an uninitialized variable in Go language.***

        **示例:**

        ```go
        // Go program to illustrate
        // concept of variable
        package main

        import "fmt"

        func main() {

            // Variable declared and 
            // initialized without expression
            var myvariable1 int
            var myvariable2 string
            var myvariable3 float64

            // Display the zero-value of the variables
            fmt.Printf("The value of myvariable1 is : %d\n",
                                             myvariable1)

            fmt.Printf("The value of myvariable2 is : %s\n",
                                             myvariable2)

            fmt.Printf("The value of myvariable3 is : %f",
                                             myvariable3)
        }
        ```

        **输出:**

        ```go
        The value of myvariable1 is : 0
        The value of myvariable2 is : 
        The value of myvariable3 is : 0.000000

        ```

    *   If you use type, then you are allowed to declare multiple variables of the same type in the single declaration.

        **示例:**

        ```go
        // Go program to illustrate
        // concept of variable
        package main
        import "fmt"

        func main() {

            // Multiple variables of the same type
            // are declared and initialized
            // in the single line
            var myvariable1, myvariable2, myvariable3 int = 2, 454, 67

           // Display the values of the variables
           fmt.Printf("The value of myvariable1 is : %d\n",
                                               myvariable1)

           fmt.Printf("The value of myvariable2 is : %d\n",
                                               myvariable2)

           fmt.Printf("The value of myvariable3 is : %d",
                                              myvariable3)
        }
        ```

        **输出:**

        ```go
        The value of myvariable1 is : 2
        The value of myvariable2 is : 454
        The value of myvariable3 is : 67

        ```

    *   If you remove type, then you are allowed to declare multiple variables of a different type in the single declaration. The type of variables is determined by the initialized values.

        **示例:**

        ```go
        // Go program to illustrate
        // concept of variable
        package main
        import "fmt"

        func main() {

        // Multiple variables of different types
        // are declared and initialized in the single line
        var myvariable1, myvariable2, myvariable3 = 2, "GFG", 67.56

        // Display the value and 
        // type of the variables
        fmt.Printf("The value of myvariable1 is : %d\n",
                                            myvariable1)

        fmt.Printf("The type of myvariable1 is : %T\n",
                                           myvariable1)

        fmt.Printf("\nThe value of myvariable2 is : %s\n",
                                             myvariable2)

        fmt.Printf("The type of myvariable2 is : %T\n",
                                           myvariable2)

        fmt.Printf("\nThe value of myvariable3 is : %f\n",
                                              myvariable3)

        fmt.Printf("The type of myvariable3 is : %T\n",
                                           myvariable3)
        }
        ```

        **输出:**

        ```go
        The value of myvariable1 is : 2
        The type of myvariable1 is : int

        The value of myvariable2 is : GFG
        The type of myvariable2 is : string

        The value of myvariable3 is : 67.560000
        The type of myvariable3 is : float64

        ```

    *   You are allowed to initialize a set of variables by the calling function that returns multiple values.

        **示例:**

        ```go
        // Here, os.Open function return a
        // file in i variable and an error
        // in j variable
        var i, j = os.Open(name)

        ```** 
2.  ****Using short variable declaration:** The local variables which are declared and initialize in the functions are declared by using short variable declaration.

    **语法:**

    ```go
    variable_name:= expression
    ```

    **注意:**请不要混淆 *:=* 和 *=* 因为 *:=* 是声明， *=* 是赋值。

    **要点:**

    *   In the above expression, the type of the variable is determined by the type of the expression.

        **示例:**

        ```go
        // Go program to illustrate
        // concept of variable
        package main
        import "fmt"

        func main() {

        // Using short variable declaration
        myvar1 := 39 
        myvar2 := "GeeksforGeeks" 
        myvar3 := 34.67

        // Display the value and type of the variables
        fmt.Printf("The value of myvar1 is : %d\n", myvar1)
        fmt.Printf("The type of myvar1 is : %T\n", myvar1)

        fmt.Printf("\nThe value of myvar2 is : %s\n", myvar2)
        fmt.Printf("The type of myvar2 is : %T\n", myvar2)

        fmt.Printf("\nThe value of myvar3 is : %f\n", myvar3)
        fmt.Printf("The type of myvar3 is : %T\n", myvar3)
        }
        ```

        **输出:**

        ```go
        The value of myvar1 is : 39
        The type of myvar1 is : int

        The value of myvar2 is : GeeksforGeeks
        The type of myvar2 is : string

        The value of myvar3 is : 34.670000
        The type of myvar3 is : float64

        ```

    *   由于简洁和灵活，大多数局部变量都是通过使用短变量声明来声明和初始化的。
    *   变量的 var 声明用于那些需要不同于初始值设定项表达式的显式类型的局部变量，或者用于那些值稍后被赋值并且初始化值不重要的变量。
    *   Using short variable declaration you are allowed to declare multiple variables in the single declaration.

        **示例:**

        ```go
        // Go program to illustrate
        // concept of variable
        package main
        import "fmt"

        func main() {

        // Using short variable declaration
        // Multiple variables of same types
        // are declared and initialized in 
        // the single line
        myvar1, myvar2, myvar3 := 800, 34, 56

        // Display the value and 
        // type of the variables
        fmt.Printf("The value of myvar1 is : %d\n", myvar1)
        fmt.Printf("The type of myvar1 is : %T\n", myvar1)

        fmt.Printf("\nThe value of myvar2 is : %d\n", myvar2)
        fmt.Printf("The type of myvar2 is : %T\n", myvar2)

        fmt.Printf("\nThe value of myvar3 is : %d\n", myvar3)
        fmt.Printf("The type of myvar3 is : %T\n", myvar3)
        }
        ```

        **输出:**

        ```go
        The value of myvar1 is : 800
        The type of myvar1 is : int

        The value of myvar2 is : 34
        The type of myvar2 is : int

        The value of myvar3 is : 56
        The type of myvar3 is : int

        ```

    *   In a short variable declaration, you are allowed to initialize a set of variables by the calling function that returns multiple values.

        **示例:**

        ```go
        // Here, os.Open function return 
        // a file in i variable and an 
        // error in j variable
        i, j := os.Open(name)

        ```

    *   A short variable declaration acts like an assignment only when for those variables that are already declared in the same lexical block. The variables that are declared in the outer block are ignored. And at least one variable is a new variable out of these two variables as shown in the below example.

        **示例:**

        ```go
        // Go program to illustrate
        // concept of variable
        package main
        import "fmt"

        func main() {

        // Using short variable declaration
        // Here, short variable declaration acts
        // as an assignment for myvar2 variable
        // because same variable present in the same block
        // so the value of myvar2 is changed from 45 to 100
        myvar1, myvar2 := 39, 45 
        myvar3, myvar2 := 45, 100

        // If you try to run the commented lines,
        // then compiler will gives error because
        // these variables are already defined
        // myvar1, myvar2 := 43, 47
        // myvar2:= 200

        // Display the values of the variables
        fmt.Printf("The value of myvar1 and myvar2 is : %d %d\n",
                                                  myvar1, myvar2)

        fmt.Printf("The value of myvar3 and myvar2 is : %d %d\n",
                                                  myvar3, myvar2)
        }
        ```

        **输出:**

        ```go
        The value of myvar1 and myvar2 is : 39 100
        The value of myvar3 and myvar2 is : 45 100

        ```

    *   Using short variable declaration you are allowed to declare multiple variables of different types in the single declaration. The type of these variables are determined by the expression.

        **示例:**

        ```go
        // Go program to illustrate
        // concept of variable
        package main
        import "fmt"

        func main() {

        // Using short variable declaration
        // Multiple variables of different types
        // are declared and initialized in the single line
        myvar1, myvar2, myvar3 := 800, "Geeks", 47.56

        // Display the value and type of the variables
        fmt.Printf("The value of myvar1 is : %d\n", myvar1)
        fmt.Printf("The type of myvar1 is : %T\n", myvar1)

        fmt.Printf("\nThe value of myvar2 is : %s\n", myvar2)
        fmt.Printf("The type of myvar2 is : %T\n", myvar2)

        fmt.Printf("\nThe value of myvar3 is : %f\n", myvar3)
        fmt.Printf("The type of myvar3 is : %T\n", myvar3)

        }
        ```

        **输出:**

        ```go
        The value of myvar1 is : 800
        The type of myvar1 is : int

        The value of myvar2 is : Geeks
        The type of myvar2 is : string

        The value of myvar3 is : 47.560000
        The type of myvar3 is : float64

        ```**