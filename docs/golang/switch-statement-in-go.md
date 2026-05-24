# GO

中的 SWITCH 语句

> Original: [https://www.geeksforgeeks.org/switch-statement-in-go/](https://www.geeksforgeeks.org/switch-statement-in-go/)

Switch 语句是多路分支语句。 它提供了一种基于表达式的值(也称为 case)将执行转移到代码的不同部分的有效方法。 GO 语言支持两种类型的 Switch 语句：

1.  **表达式开关**
2.  **类型开关**

#### 表达式开关

表达式 switch 类似于 C、C++、[Java](https://www.geeksforgeeks.org/java/)语言中的 switch 语句。 它提供了一种简单的方法，可以根据表达式的值将执行分派到代码的不同部分。

**语法：**

```go
switch optstatement; optexpression{
case expression1: Statement..
case expression2: Statement..
...
default: Statement..
}

```

**要点：**

*   表达式开关中的*optStatement*和*optExpression*都是可选语句。
*   如果*optStatement*和*optExpression*都存在，则它们之间需要分号(；)。
*   如果开关不包含任何表达式，则编译器假定表达式为真。
*   可选语句，即 opt 语句，包含变量声明、增量或赋值语句或函数调用等简单语句。
*   如果可选语句中存在变量，则该变量的作用域仅限于该 switch 语句。
*   在 SWITCH 语句中，CASE 和 DEFAULT 语句不包含任何 BREAK 语句。 但是，如果您的程序需要，您可以使用 Break 和 Fall Through 语句。
*   在 switch 语句中，DEFAULT 语句是可选的。
*   如果一个案例可以包含多个值，并且这些值用逗号(，)分隔。
*   如果 case 不包含任何表达式，则编译器假定 TE 表达式为真。

**示例 1：**

```go
// Go program to illustrate the 
// concept of Expression switch
// statement
package main

import "fmt"

func main() {

    // Switch statement with both 
    // optional statement, i.e, day:=4
    // and expression, i.e, day
    switch day:=4; day{
       case 1:
       fmt.Println("Monday")
       case 2:
       fmt.Println("Tuesday")
       case 3:
       fmt.Println("Wednesday")
       case 4:
       fmt.Println("Thursday")
       case 5:
       fmt.Println("Friday")
       case 6:
       fmt.Println("Saturday")
       case 7:
       fmt.Println("Sunday")
       default: 
       fmt.Println("Invalid")
   }

}
```

发帖主题：Re：Колибри0.7.0

```go
Thursday
```

**示例 2：**

```go
// Go program to illustrate the 
// concept of Expression switch
// statement
package main

import "fmt"

func main() {
    var value int = 2

    // Switch statement without an     
    // optional statement and 
    // expression
   switch {
       case value == 1:
       fmt.Println("Hello")
       case value == 2:
       fmt.Println("Bonjour")
       case value == 3:
       fmt.Println("Namstay")
       default: 
       fmt.Println("Invalid")
   }

}
```

发帖主题：Re：Колибри0.7.0

```go
Bonjour
```

**示例 3：**

```go
// Go program to illustrate the 
// concept of Expression switch
// statement
package main

import "fmt"

func main() {
    var value string = "five"

    // Switch statement without default statement
    // Multiple values in case statement
   switch value {
       case "one":
       fmt.Println("C#")
       case "two", "three":
       fmt.Println("Go")
       case "four", "five", "six":
       fmt.Println("Java")
   }  
}
```

发帖主题：Re：Колибри0.7.0

```go
Java
```

#### 类型开关

类型开关在您想要比较类型时使用。 在此 Switch 中，case 包含要与 Switch 表达式中存在的类型进行比较的类型。

**语法：**

```go
switch optstatement; typeswitchexpression{
case typelist 1: Statement..
case typelist 2: Statement..
...
default: Statement..
}

```

**要点：**

*   可选语句(即 optStatement)类似于 switch 表达式中的语句。
*   如果一个案例可以包含多个值，并且这些值用逗号(，)分隔。
*   在类型切换语句中，CASE 和 DEFAULT 语句不包含任何 BREAK 语句。 但是，如果您的程序需要，您可以使用 Break 和 Fall Through 语句。
*   在类型切换语句中，DEFAULT 语句是可选的。
*   *类型切换表达式*是其结果为类型的表达式。
*   如果在*tyeswitchexpression*中使用：=运算符为表达式赋值，则该变量的类型取决于 CASE 子句中出现的类型。 如果 CASE 子句包含两个或多个类型，那么变量的类型就是在*tyeswitchexpression*中创建变量的类型。

**示例：**

```go
// Go program to illustrate the 
// concept of Type switch
// statement
package main

import "fmt"

func main() {
    var value interface{}
    switch q:= value.(type) {
       case bool:
       fmt.Println("value is of boolean type")
       case float64:
       fmt.Println("value is of float64 type")
       case int:
       fmt.Println("value is of int type")
       default:
       fmt.Printf("value is of type: %T", q)

   }
}
```

发帖主题：Re：Колибри0.7.0

```go
value is of type: <nil>
```