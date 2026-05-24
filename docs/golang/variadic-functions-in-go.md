# 围棋中的变量函数

> Original: [https://www.geeksforgeeks.org/variadic-functions-in-go/](https://www.geeksforgeeks.org/variadic-functions-in-go/)

使用不同数量的参数调用的函数称为变量函数。 或者换句话说，允许用户在可变函数中传递零个或多个参数。 *fmt.Printf*是可变函数的示例，它在开始时需要一个固定参数，之后它可以接受任意数量的参数。
**要点：**

*   在变量函数的声明中，最后一个参数的类型前面有一个省略号，即(**…。** ))。 它指示可以在此类型的任意数量的参数上调用该函数。
    **语法：**和

```go
function function_name(para1, para2...type)type{
// code...
}
```

*   函数*…内部。 类型*的行为类似于切片。 例如，假设我们有一个函数签名，即 Add(b…。 Int)int，现在是[]int 类型的参数。
*   您还可以在变量函数中传递现有的片。 为此，我们将完整数组的一部分传递给函数，如下面的*示例 2*所示。
*   如果不在变量函数中传递任何参数，则函数内部的切片为空。
*   可变函数通常用于字符串格式化。
*   您还可以在变量函数中传递多个切片。
*   不能将可变参数用作返回值，但可以将其作为切片返回。

**示例 1：**

## 电容 / 碳

```go
// Go program to illustrate the
// concept of variadic function
package main

import(
    "fmt"
    "strings"
)

// Variadic function to join strings
func joinstr(element...string)string{
    return strings.Join(element, "-")
}

func main() {

  // zero argument
   fmt.Println(joinstr())

   // multiple arguments
   fmt.Println(joinstr("GEEK", "GFG"))
   fmt.Println(joinstr("Geeks", "for", "Geeks"))
   fmt.Println(joinstr("G", "E", "E", "k", "S"))

}
```

发帖主题：Re：Колибри0.7.8.0

```go
GEEK-GFG
Geeks-for-Geeks
G-E-E-k-S
```

**示例 2：**

## 电容 / 碳

```go
// Go program to illustrate the
// concept of variadic function
package main

import(
    "fmt"
    "strings"
)

// Variadic function to join strings
func joinstr(element...string)string{
    return strings.Join(element, "-")
}

func main() {

   // pass a slice in variadic function
   element:= []string{"geeks", "FOR", "geeks"}
   fmt.Println(joinstr(element...))
}
```

发帖主题：Re：Колибри0.7.8.0

```go
geeks-FOR-geeks
```

**当我们使用变量函数时：**

*   当您想要在函数中传递切片时，可以使用变量函数。
*   当我们不知道参数的数量时，使用变量函数。
*   当你在你的程序中使用可变函数时，它会增加你的程序的可读性。