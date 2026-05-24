# 用 Go 语言返回多个值的函数

> 原文:[https://www . geesforgeks . org/function-returning-multi-values-in-go-language/](https://www.geeksforgeeks.org/function-returning-multiple-values-in-go-language/)

在 Go 语言中，您可以使用 return 语句从一个[函数](https://www.geeksforgeeks.org/functions-in-go-language/)返回多个值。或者换句话说，在函数中，一个 return 语句可以返回多个值。返回值的类型类似于参数列表中定义的参数类型。

**语法:**

```go
func function_name(parameter_list)(return_type_list){
     // code...
}

```

*这里，*

*   **函数 _ 名称:**是函数的名称。
*   **参数表:**包含功能参数的名称和类型。
*   **return_type_list:** 可选，包含函数返回的值的类型。如果在函数中使用 return_type，那么就需要在函数中使用 return 语句。

**示例:**

```go
// Go program to illustrate how a
// function return multiple values
package main

import "fmt"

// myfunc return 3 values of int type
func myfunc(p, q int)(int, int, int ){
    return p - q, p * q, p + q 
}

// Main Method
func main() {

    // The return values are assigned into 
    // three different variables
   var myvar1, myvar2, myvar3 = myfunc(4, 2)

   // Display the values
   fmt.Printf("Result is: %d", myvar1 )
   fmt.Printf("\nResult is: %d", myvar2)
   fmt.Printf("\nResult is: %d", myvar3)
}
```

**输出:**

```go
Result is: 2
Result is: 8
Result is: 6

```

#### 给返回值命名

在 Go 语言中，允许您为返回值提供名称。您也可以在代码中使用这些变量名。没有必要用返回语句来写这些名字，因为 Go 编译器会自动理解这些变量必须调度回来。这种回报被称为裸回报。最少的回报减少了程序中的重复。

**语法:**

```go
func function_name(para1, para2 int)(name1 int, name2 int){
    // code...
}

or

func function_name(para1, para2 int)(name1, name2 int){
   // code...
}

```

这里，*名称 1**名称 2* 是返回值的名称，para1 和 para2 是函数的参数。

**示例:**

```go
// Go program to illustrate how to
// give names to the return values
package main

import "fmt"

// myfunc return 2 values of int type
// here, the return value name 
// is rectangle and square
func myfunc(p, q int)( rectangle int, square int ){
    rectangle = p*q
    square = p*p
    return  
}

func main() {

    // The return values are assigned into 
    // two different variables
   var area1, area2 = myfunc(2, 4)

   // Display the values
   fmt.Printf("Area of the rectangle is: %d", area1 )
   fmt.Printf("\nArea of the square is: %d", area2)

}
```

**输出:**

```go
Area of the rectangle is: 8
Area of the square is: 4

```