# Go 变量

> 原文: [https://www.geeksforgeeks.org/go-variables/](https://www.geeksforgeeks.org/go-variables/)

典型的程序使用各种值，这些值在执行过程中可能会改变。例如，对用户输入的值进行一些操作的程序。一个用户输入的值可能与另一个用户输入的值不同。因此，这使得有必要使用变量，因为另一个用户可能不会使用相同的值。当用户输入一个将在操作过程中使用的新值时，可以将其临时存储在计算机的随机存取存储器中，并且在整个执行过程中，这部分存储器中的这些值会发生变化，因此出现了另一个术语，称为**变量**。因此，基本上，变量是可以在运行时更改的信息的占位符。变量允许检索和操作存储的信息。

## 变量命名规则

*   变量名必须以字母或下划线(`_`)开头。并且名称可以包含字母“a-z”或“A-Z”或数字 0-9 以及字符“`_`”。

```go
Geeks, geeks, _geeks23  // valid variable
123Geeks, 23geeks      // invalid variable
```

*   变量名不应以数字开头。

```go
234geeks  // illegal variable
```

*   变量的名称区分大小写。

```go
geeks and Geeks are two different variables
```

*   关键字不允许用作变量名。
*   变量名称的长度没有限制，但建议仅使用 4-15 个字母的最佳长度。

## 声明变量

在 Go 语言中，变量以两种不同的方式创建:

### 1. 使用 `var` 关键字

在 Go 语言中，变量使用 `var` 关键字创建，指定类型，关联名称并提供其初始值。

**语法:**

```go
var variable_name type = expression
```

**要点:**

*   在上面的语法中，要么`类型`要么`=`表达式可以移除，但不是两者都可以，可以在变量的声明中移除。
*   如果类型被移除，那么变量的类型由表达式中的初始化值决定。

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

*   如果表达式被移除，那么变量保存该类型的零值，例如数字为零，布尔值为`false`，字符串为`""`，接口和引用类型为`nil`。因此，在 Go 语言中**没有未初始化变量的概念**。

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

*   如果你使用类型，那么你可以在单个声明中声明多个相同类型的变量。

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

*   如果你移除类型，那么你可以在单个声明中声明多个不同类型的变量。变量的类型由初始化值决定。

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

*   你可以通过调用返回多个值的函数来初始化一组变量。

**示例:**

```go
// Here, os.Open function return a
// file in i variable and an error
// in j variable
var i, j = os.Open(name)
```

### 2. 使用短变量声明

在函数中声明和初始化的局部变量使用短变量声明来声明。

**语法:**

```go
variable_name:= expression
```

**注意:** 请不要混淆`:=`和`=`，因为`:=`是声明，`=`是赋值。

**要点:**

*   在上面的表达式中，变量的类型由表达式的类型决定。

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
*   变量的 `var` 声明用于那些需要不同于初始值设定项表达式的显式类型的局部变量，或者用于那些值稍后被赋值并且初始化值不重要的变量。
*   使用短变量声明，你可以在单个声明中声明多个变量。

**示例:**

## 短变量声明示例

```go
// Go program to illustrate
// concept of variable
package main
import "fmt"

func main() {
    // Using short variable declaration
    // Multiple variables of same types
    // are declared and initialized in the single line
    myvar1, myvar2, myvar3 := 800, 34, 56

    // Display the value and type of the variables
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

### 从函数返回值初始化

在短变量声明中，允许通过调用返回多个值的函数来初始化一组变量。

**示例:**

```go
// Here, os.Open function return
// a file in i variable and an
// error in j variable
i, j := os.Open(name)
```

### 在同一代码块中作为赋值操作

短变量声明仅当针对那些已在同一词法块中声明的变量时，其行为才类似于赋值。外部块中声明的变量将被忽略。并且这两个变量中至少有一个是新变量，如下例所示。

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

### 声明不同类型的多个变量

使用短变量声明，可以在单个声明中声明多个不同类型的变量。这些变量的类型由表达式决定。

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
```