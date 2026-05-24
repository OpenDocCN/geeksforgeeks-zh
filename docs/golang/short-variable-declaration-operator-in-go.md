# Go

中的短变量声明运算符(:=)

> 原文:[https://www . geesforgeks . org/short-variable-declaration-operator-in-go/](https://www.geeksforgeeks.org/short-variable-declaration-operator-in-go/)

[Golang](https://www.geeksforgeeks.org/go-programming-language-introduction/) 中的短变量声明运算符(:=)用于创建具有专有名称和初始值的变量。使用此运算符的主要目的是声明和初始化函数内部的**局部变量**，并缩小变量的范围。变量的类型由表达式的类型决定。 [var 关键字](https://www.geeksforgeeks.org/var-keyword-in-go/)也用于创建特定类型的变量。所以你可以说有两种方法可以在 Golang 中创建变量，如下所示:

*   使用 var 关键字
*   使用短变量声明运算符(:=)

在本文中，我们将只讨论短变量声明运算符。要了解 var 关键字，可以参考 Go 中的 [**var 关键字。你也可以阅读**](https://www.geeksforgeeks.org/var-keyword-in-go/)**[**var 关键字和短变量声明运算符**](https://www.geeksforgeeks.org/difference-between-var-keyword-and-short-declaration-operator-in-golang/) 的区别，从而对两者的使用有一个正确的认识。**

**使用短变量声明运算符的语法:**

```go
variable_name := expression or value
```

这里，您必须在声明之后初始化变量。但是使用 var 关键字可以避免在声明时初始化。没有**需要提变量**的类型。右侧的表达式或值用于计算变量的类型。

**示例:**这里，我们使用短声明运算符声明变量，并且不指定变量的类型。变量的类型由 *:=* 运算符右侧的表达式类型决定。

## 去

```go
// Go program to illustrate the use
// of := (short declaration
// operator)
package main

import "fmt"

func main() {

    // declaring and initializing the variable 
    a := 30

    // taking a string variable
    Language: = "Go Programming"

    fmt.Println("The Value of a is: ", a)
    fmt.Println("The Value of Language is: ", Language)

}
```

**输出:**

```go
The Value of a is:  30
The Value of Language is:  Go Programming
```

### 使用短声明运算符声明多个变量(:=)

短声明运算符也可用于在单个声明中声明相同类型或不同类型的多个变量。这些变量的类型由 *:=* 运算符右侧的表达式计算。

**示例:**

## 去

```go
// Go program to illustrate how to use := short
// declaration operator to declare multiple
// variables into a single declaration statement
package main

import "fmt"

func main() {

// multiple variables of same type(int)
geek1, geek2, geek3 := 117, 7834, 5685

// multiple variables of different types
geek4, geek5, geek6 := "GFG", 859.24, 1234

// Display the value and
// type of the variables
fmt.Printf("The value of geek1 is : %d\n", geek1)
fmt.Printf("The type of geek1 is : %T\n", geek1)

fmt.Printf("\nThe value of geek2 is : %d\n", geek2)
fmt.Printf("The type of geek2 is : %T\n", geek2)

fmt.Printf("\nThe value of geek3 is : %d\n", geek3)
fmt.Printf("The type of geek3 is : %T\n", geek3)

fmt.Printf("\nThe value of geek4 is : %s\n", geek4)
fmt.Printf("The type of geek4 is : %T\n", geek4)

fmt.Printf("\nThe value of geek5 is : %f\n", geek5)
fmt.Printf("The type of geek5 is : %T\n", geek5)

fmt.Printf("\nThe value of geek6 is : %d\n", geek6)
fmt.Printf("The type of geek6 is : %T\n", geek6)

}
```

**输出:**

```go
The value of geek1 is : 117
The type of geek1 is : int

The value of geek2 is : 7834
The type of geek2 is : int

The value of geek3 is : 5685
The type of geek3 is : int

The value of geek4 is : GFG
The type of geek4 is : string

The value of geek5 is : 859.240000
The type of geek5 is : float64

The value of geek6 is : 1234
The type of geek6 is : int
```

**要点:**

*   当*左侧至少有一个变量是新声明的:=运算符*时，可以使用短声明运算符。一个简短的变量声明操作符的行为类似于对那些已经在同一个词法块中声明的变量的赋值。为了更好地理解这个概念，让我们举个例子。
    **例 1:** 下面的程序会给出一个错误，因为*左侧没有新的变量:=运算符*。

## 去

```go
// Go program to illustrate the concept
// of short variable declaration
package main

import "fmt"

func main() { 

    // taking two variables
    p, q := 100, 200

    fmt.Println("Value of p ", p, "Value of q ", q)

    // this will give an error as
    // there are no new variable
    // on the left-hand side of :=
    p, q := 500, 600

    fmt.Println("Value of p ", p, "Value of q ", q)
}
```

**错误:**

> 。/prog.go:17:10:左侧无新变量:=

**示例 2:** 在下面的程序中，您可以看到代码行 *geek3，geek2 := 456，200* 将正常工作，没有任何错误，因为在:=运算符的左侧至少有一个新变量，即 *geek3* 。

## 去

```go
// Go program to show how to use
// short variable declaration operator
package main

import "fmt"

func main() {

// Here, short variable declaration acts
// as an assignment for geek1 variable
// because same variable present in the same block
// so the value of geek2 is changed from 100 to 200
geek1, geek2 := 78, 100

// here, := is used as an assignment for geek2
// as it is already declared. Also, this line
// will work fine as geek3 is newly created
// variable
geek3, geek2 := 456, 200

// If you try to run the commented lines,
// then compiler will gives error because
// these variables are already defined
// geek1, geek2 := 745, 956
// geek3 := 150

// Display the values of the variables
fmt.Printf("The value of geek1 and geek2 is : %d %d\n", geek1, geek2)

fmt.Printf("The value of geek3 and geek2 is : %d %d\n", geek3, geek2)
}
```

**输出:**

```go
The value of geek1 and geek2 is : 78 200
The value of geek3 and geek2 is : 456 200
```

*   Go 是一种强类型语言，因为不能将另一种类型的值赋给声明的变量。
    **例:**

## 去

```go
// Go program to show how to use
// short variable declaration operator
package main

import "fmt"

func main() {

    // taking a variable of int type
    z := 50

    fmt.Printf("Value of z is %d", z)

    // reassigning the value of string type
    // it will give an error
    z := "Golang"
}
```

**错误:**

> 。/prog.go:16:4:左侧无新变量:=
> 。/prog.go:16:7:在赋值
> 中不能使用“Golang”(类型字符串)作为类型 int

*   在一个简短的变量声明中，允许通过调用返回多个值的函数来初始化一组变量。或者你可以说变量也可以被赋值，在运行时被评估。
    **例:**

```go
// Here, math.Max function return 
// the maximum number in i variable
i := math.Max(x, y)
```

### 局部变量还是全局变量？

借助短变量声明运算符(:=) **只能声明只有块级作用域的局部变量**。通常，局部变量在功能块中声明。如果您试图使用短声明操作符声明全局变量，那么您将会得到一个错误。

**例 1:**

## 去

```go
// Go program to show the use of := operator
// to declare local variables
package main

import "fmt"

// using var keyword to declare 
// and initialize the variable
// it is package or you can say 
// global level scope
var geek1 = 900

// using short variable declaration
// it will give an error
geek2 := 200

func main() {

// accessing geek1 inside the function
fmt.Println(geek1)

// accessing geek2 inside the function
fmt.Println(geek2)

}
```

**错误:**

> 。/prog.go:15:1:语法错误:函数体外非声明语句

**例 2:**

## 去

```go
// Go program to show the use of := operator
// to declare local variables
package main

import "fmt"

// using var keyword to declare 
// and initialize the variable
// it is package or you can say 
// global level scope
var geek1 = 900

func main() {

// using short variable declaration
// inside the main function
// it has local scope i.e. can't
// accessed outside the main function
geek2 := 200

// accessing geek1 inside the function
fmt.Println(geek1)

// accessing geek2 inside the function
fmt.Println(geek2)

}
```

**输出:**

```go
900
200
```