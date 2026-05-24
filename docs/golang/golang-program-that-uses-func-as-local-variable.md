# 使用 func 作为局部变量的 Golang 程序

> 原文:[https://www . geesforgeks . org/golang-使用-func-as-local-variable/](https://www.geeksforgeeks.org/golang-program-that-uses-func-as-local-variable/)

函数执行一个特定的任务，一段定义一次的代码可以被重用。函数用于通过将代码分解成小的和可理解的任务来使代码更容易理解。功能也称为**方法**、**子程序**或**程序**。

Go 编程语言中函数定义的一般形式如下-

```go
func function_name( [parameter list] ) [return_types]
{
   body of the function
}
```

Go 编程语言中的函数定义，这里定义函数的某些部分-

*   **函数:**开始函数的声明。
*   **函数名:**函数名包含括号，可能包含参数。这是函数的实际名称。
*   **参数:**参数是函数定义中的命名实体，指定函数可以接受的参数。参数是可选的；也就是说，函数可能不包含参数。
*   **返回类型:**还必须指定返回数据类型。return_types 是函数返回值的数据类型列表。
*   **函数体:**它包含定义函数作用的语句集合。

要调用一个函数，它需要传递所需的参数及其函数名。这个函数接受两个参数 number1 和 number2，并返回两者之间的最大值？

**例**

```go
package main

import "fmt"

func main() {

    // local variable definition
    var x int = 150
    var y int = 360
    var ret int

    // calling a function to get max value
    // and storing its value in a variable
    ret = max(x, y)

    fmt.Printf("Maximum value is : %d\n", ret)
}

// function returning the max between two numbers
func max(number1, number2 int) int {

    var result int

    if number1 > number2 {
        result = number1
    } else {
        result = number2
    }
    return result
}
```

**输出:**

```go
Maximum value is : 360
```

我们可以将 func 变量作为参数传递给需要 func 参数的方法，如下例所示

```go
// Golang program that uses func
// as a local variable
package main

import (
    "fmt"
    "strings"
)

func main() {

    // assigning function f to a variable f1
    f1 := func(f rune) bool {

        // Return true if underscore
        // or space rune.
        return f == '_' ||
            f == ' '
    }

    val := "geeks1 geeks2"

    // Pass func object to IndexFunc method.
    // Here f1 is a function argument
    finalresult := strings.IndexFunc(val, f1)
    fmt.Println(finalresult)

    val = "geeks1_geeks2"
    finalresult = strings.IndexFunc(val, f1)
    fmt.Println(finalresult)
}
```

**输出:**

```go
6
6

```