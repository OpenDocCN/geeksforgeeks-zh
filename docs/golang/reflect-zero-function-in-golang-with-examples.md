# 反映。Golang 中的 Zero()函数示例

> 原文:[https://www . geesforgeks . org/reflect-zero-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-zero-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 Zero()** 函数用于获取表示指定类型的零值的值。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func Zero(typ Type) Value
> 
> ```
> 
> **参数:**该函数取以下参数:
> 
> *   **类型:**该参数为类型。
> 
> **返回值:**该函数返回代表指定类型零值的值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Zero() Function

package main

import (
    "fmt"
    "reflect"
)

func main() {
    s := struct{ A int }{0}
    field := reflect.ValueOf(s).Field(0)

    fmt.Println(field.Interface())

    // use of Zero() method
    fmt.Println(reflect.Zero(field.Type()))

    fmt.Println(reflect.DeepEqual(field.Interface(), reflect.Zero(field.Type())))
}

```

**输出:**

```go
0
0
false

```

**例 2:**

```go
// Golang program to illustrate
// reflect.Zero() Function

package main

import (
    "fmt"
    "reflect"
)

func main() {
    s := struct{ A int }{0}
    field := reflect.ValueOf(s).Field(0)

    fmt.Println(field.Interface())

    // use of Zero() method
    fmt.Println(reflect.Zero(field.Type()))
    fmt.Println(reflect.TypeOf(field.Interface()))

    // use of Zero() method
    fmt.Println(reflect.TypeOf(reflect.Zero(field.Type())))

    // use of Zero() method
    fmt.Println(reflect.DeepEqual(field.Interface(),
                       reflect.Zero(field.Type())))

    fmt.Println(reflect.DeepEqual(field.Interface(), 
            int(reflect.Zero(field.Type()).Int())))
    fmt.Println(reflect.DeepEqual(s, struct{ A int }{} ))
    fmt.Println(reflect.DeepEqual(s, struct{ A int }{0} ))
}
```

**输出:**

```go
0
0
int
reflect.Value
false
true
true
true

```