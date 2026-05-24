# 在 Golang 中查找对象类型的不同方法

> 原文:[https://www . geeksforgeeks . org/不同的方法来找到 golang 中的对象类型/](https://www.geeksforgeeks.org/different-ways-to-find-the-type-of-an-object-in-golang/)

[**Go**](https://www.geeksforgeeks.org/go-programming-language-introduction/) 没有类类型的概念，因此，你在 Go 中没有对象。您可以将 Go 中的任何数据类型作为对象引用。Go 提供多种[数据类型](https://www.geeksforgeeks.org/data-types-in-go/)，如 int8、int16、int32、int64、float64、string、bool 等。有三种不同的方法可以在运行时在 Go 中找到变量的类型。

### 1.将 fmt 用于字符串类型描述

[fmt](https://golang.org/pkg/fmt/) 包中的 *%T* 是值类型的 Go 语法表示。您可以使用%T 来查找变量类型。

**语法:**

```go
func typeofobject(x interface{}) {
    fmt.Sprintf("%T", x)
}

```

**例 1:**

```go
// Golang program to find the variable type
package main

// importing required packages
import (
    "fmt"
)

// main function
func main() {
    f := true
    st := ""
    a := 1
    d := 1.0
    arr := []string{"Go", "Is", "Fun"}

    fmt.Printf("%T\n", f)
    fmt.Printf("%T\n", st)
    fmt.Printf("%T\n", a)
    fmt.Printf("%T\n", d)
    fmt.Printf("%T\n", arr)
}
```

**输出:**

```go
bool
string
int
float64
[]string

```

**例 2:**

```go
// Golang program to show how to find
// the type of an object
package main

// importing required packages
import (
    "fmt"
)

func main() {
    types := []interface{}{"Code", 10, true, 10.55}
    for _, x := range types {
        fmt.Printf("%T\n", x)
    }
}
```

**输出:**

```go
string
int
bool
float64

```

**注意:**一个空的[界面](https://www.geeksforgeeks.org/interfaces-in-golang/)由界面{}表示，可以用来保存任何类型的值。

### 2.使用反射包

您也可以使用[反射包](https://golang.org/pkg/reflect/)，它实现运行时反射，从而允许程序操作任意类型的对象。*反映。*和*的类型反映。值为(x)。Kind()* 函数帮助我们找到需要的变量类型。

**语法:**

```go
func typeofobject(x interface{}){
    fmt.Println(reflect.TypeOf(x))
}

```

或者

```go
func typeofobject(x interface{}){
    fmt.Println(reflect.ValueOf(x).Kind())
}

```

**例 1:**

```go
// Golang program to demonstrate
// the use of reflect.TypeOf function
package main

//importing reflect package
import (
    "fmt"
    "reflect"
)

func main() {
    f := true
    st := ""
    a := 1
    d := 1.0
    arr := []string{"Go", "Is", "Fun"}

    fmt.Println(reflect.TypeOf(f))
    fmt.Println(reflect.TypeOf(st))
    fmt.Println(reflect.TypeOf(a))
    fmt.Println(reflect.TypeOf(d))
    fmt.Println(reflect.TypeOf(arr))
}
```

**输出:**

```go
bool
string
int
float64
[]string

```

我们可以使用 ValueOf()进行类似的操作。Kind()函数。

**例 2:**

```go
// Golang program to demonstrate
// the use of reflect.ValueOf(x).Kind() function
package main

import (
    "fmt"
    "reflect"
)

func main() {
    f := true
    st := ""
    a := 1
    d := 1.0
    arr := []string{"Coding", "In", "Go"}

    fmt.Println(reflect.ValueOf(f).Kind())
    fmt.Println(reflect.ValueOf(st).Kind())
    fmt.Println(reflect.ValueOf(a).Kind())
    fmt.Println(reflect.ValueOf(d).Kind())
    fmt.Println(reflect.ValueOf(arr).Kind())
}
```

**输出:**

```go
bool
string
int
float64
slice

```

**例 3:**

```go
package main

// importing required packages
import (
    "fmt"
    "reflect"
)

func main() {
    types := []interface{}{"Code", true, 5, 3.14, []int{1, 2, 3, 4}}
    for _, x := range types {
        fmt.Println(reflect.ValueOf(x).Kind())
    }
}
```

**输出:**

```go
string
bool
int
float64
slice

```

### 3.使用类型断言

您可以使用一个[类型开关](https://www.geeksforgeeks.org/switch-statement-in-go/)来做几个类型断言。类型开关串联使用几个类型断言，并运行第一个匹配的类型。在此开关中，案例包含要与开关表达式中的类型进行比较的类型，如果没有匹配的案例，则计算默认案例。

**语法:**

```go
switch optstatement; typeswitchexpression{
case typelist 1: Statement..
case typelist 2: Statement..
...
default: Statement..
}

```

**示例:**

```go
// Golang program to check the object type
// using type switch
package main

//importing required packages
import (
    "fmt"
)

func main() {
    types := []interface{}{"Code", true, 5, 3.14, []int{1, 2, 3}}

    for _, x := range types {
        // type switch with multiple cases
        switch x.(type) {
        case int:
            fmt.Println("int:", x)
        case float64:
            fmt.Println("float64:", x)
        case string:
            fmt.Println("string:", x)
        case bool:
            fmt.Println("bool:", x)
        default:
            fmt.Printf("data type: %T", x)
        }
    }
}
```

**输出:**

```go
string: Code
bool: true
int: 5
float64: 3.14
data type: []int

```