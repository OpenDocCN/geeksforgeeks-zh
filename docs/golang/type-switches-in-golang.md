# 在 GoLang

中键入开关

> Original: [https://www.geeksforgeeks.org/type-switches-in-golang/](https://www.geeksforgeeks.org/type-switches-in-golang/)

[**Switch**](https://www.geeksforgeeks.org/switch-statement-in-go/)是一个多路分支语句，用来代替多个 if-Else 语句，但也可以用来找出接口变量的动态类型。
类型开关是一种构造，它执行多个类型断言来确定变量的类型(而不是值)，并运行指定类型的第一个匹配的开关用例。 它在我们不知道接口{}类型可能是什么时使用。
**示例 1：**

## 电容 / 碳

```go
// Golang program to illustrate the
// concept of type switches
package main

import (
    "fmt"
)

// main function
func main() {

    // an interface that has
    // a string value
    var value interface{} = "GeeksforGeeks"

    // type switch to find
    // out interface{} type
    switch t := value.(type){

        case int64:

            // if type is an integer
            fmt.Println("Type is an integer:", t)

        case float64:

            // if type is a floating point number
            fmt.Println("Type is a float:", t)

        case string:

            // if type is a string
            fmt.Println("Type is a string:", t)

        case nil:

            // if type is nil (zero-value)
            fmt.Println("Type is nil.")

        case bool:

            // if type is a boolean
            fmt.Println("Type is a bool:", t)

        default:

            // if type is other than above
            fmt.Println("Type is unknown!")
    }
}
```

发帖主题：Re：Колибри0.7.8.0

```go
Type is a string: GeeksforGeeks
```

开关可以有多个不同类型的值用例，并用于为许多相似的用例选择公共代码块。
**注意：**Golang 不需要在开关中的每个大小写结尾都使用‘Break’关键字。
**示例 2：**

## 电容 / 碳

```go
// Golang program to illustrate the
// concept of type switch with
// multiple value cases
package main

import (
    "fmt"
)

// function which implements type
// switch with multiple cases value
func find_type(value interface{}) {

    // type switch to find
    // out interface{} type
    switch t := value.(type) {

        case int, float64:

            // type is an int or float
            fmt.Println("Type is a number, either an int or a float:", t)

        case string, bool:

            // type is a string or bool
            fmt.Println("Type is either a string or a bool:", t)

        case *int, *bool:

            // type is either an int pointer
            // or a bool pointer
            fmt.Println("Type is a pointer to an int or a bool:", t)

        default:

            // type of the interface is unknown
            fmt.Println("Type unknown!")
    }
}

// main function
func main() {

    // an interface that has
    // a string value
    var v interface{} = "GeeksforGeeks"

    // calling the find_type method
    // to determine type of interface
    find_type(v)

    // re-assigning v with a
    // float64 value
    v = 34.55

    find_type(v)
}
```

发帖主题：Re：Колибри0.7.8.0

```go
Type is either a string or a bool: GeeksforGeeks
Type is a number, either an int or a float: 34.55
```