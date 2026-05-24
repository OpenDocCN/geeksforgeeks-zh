# 反映。Golang 中的 MethodByName()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-method by name-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-methodbyname-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 MethodByName()** 函数用于获取给定名称的 v 的方法对应的函数值。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) MethodByName(name string) Value
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回给定名称的 v 的方法对应的函数值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.MethodByName() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
type T struct {}

func (t *T) GFG() {
    fmt.Println("GeeksForGeeks")
}

func main() {
    var t T
    reflect.ValueOf(&t).MethodByName("GFG").Call([]reflect.Value{})
}
```

**输出:**

```go
GeeksForGeeks

```

**例 2:**

```go
// Golang program to illustrate
// reflect.MethodByName() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function

type YourT2 struct {}
func (y YourT2) MethodFoo(i int, oo string) {
    fmt.Println(i)
    fmt.Println(oo)
}

func Invoke(any interface{}, name string, args... interface{}) {
    inputs := make([]reflect.Value, len(args))
    for i, _ := range args {
        inputs[i] = reflect.ValueOf(args[i])
    }
    reflect.ValueOf(any).MethodByName(name).Call(inputs)
}

func main() {
     Invoke(YourT2{}, "MethodFoo", 10, "Geekforgeeks")
}
```

**输出:**

```go
10
Geekforgeeks

```