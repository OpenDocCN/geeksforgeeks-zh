# 在 Golang

中键入断言

> Original: [https://www.geeksforgeeks.org/type-assertions-in-golang/](https://www.geeksforgeeks.org/type-assertions-in-golang/)

Golang 中的类型断言提供对接口变量的确切类型的访问。 如果接口中已经存在该数据类型，则它将检索接口持有的实际数据类型值。 类型断言采用接口值，并从中提取指定显式类型的值。 基本上，它是用来消除接口变量的歧义的。

**语法：**

```go
t := value.(typeName)

```

其中，*值*是其类型必须是接口的变量，*TypeName*是我们要检查的具体类型，基础 TypeName 值被赋给变量*t*。

**示例 1：**

```go
// Golang program to illustrate 
// the concept of type assertions
package main

import (
    "fmt"
)

// main function
func main() {

    // an interface that has 
    // a string value
    var value interface{} = "GeeksforGeeks"

    // retrieving a value
    // of type string and assigning
    // it to value1 variable
    var value1 string = value.(string)

    // printing the concrete value
    fmt.Println(value1)

    // this will panic as interface
    // does not have int type
    var value2 int = value.(int)

    fmt.Println(value2)
}
```

发帖主题：Re：Колибри0.7.0

```go
GeeksforGeeks
panic: interface conversion: interface {} is string, not int

```

在上面的代码中，由于 Value 接口不包含 int 类型，因此语句触发了死机，类型断言失败。 要检查接口值是否包含特定类型，类型断言可以返回两个值，带有 TypeName 值的变量和报告断言是否成功的布尔值。 下面的示例显示了这一点：

**示例 2：**

```go
// Golang program to show type
// assertions with error checking
package main

import (
    "fmt"
)

// main function
func main() {

    // an interface that has 
    // an int value
    var value interface{} = 20024

    // retrieving a value
    // of type int and assigning
    // it to value1 variable
    var value1 int = value.(int)

    // printing the concrete value
    fmt.Println(value1)

    // this will test if interface
    // has string type and
    // return true if found or
    // false otherwise
    value2, test := value.(string)
    if test {

        fmt.Println("String Value found!")
        fmt.Println(value2)
    } else {

        fmt.Println("String value not found!")
    }
}
```

发帖主题：Re：Колибри0.7.0

```go
20024
String value not found!

```