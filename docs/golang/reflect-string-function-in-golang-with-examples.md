# 反映。Golang 中的 String()函数示例

> 原文:[https://www . geesforgeks . org/reflect-string-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-string-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 String()** 函数用于获取字符串 v 的基础值，作为字符串。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) String() string
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**这个函数以字符串的形式返回字符串 v 的基础值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.String() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    var k = reflect.TypeOf(0)
    var e = reflect.TypeOf("")

    //use of String method
    fmt.Println(reflect.FuncOf([]reflect.Type{k}, 
              []reflect.Type{e}, false).String())
}
```

**输出:**

```go
func(int) string

```

**例 2:**

```go
// Golang program to illustrate
// reflect.String() Function 

package main

import (
    "fmt"
    "reflect"
)

type Struct1 struct {
    Var1       string
    Var2       string
    Var3       float64
    Var4       float64
}

// Main function 
func main() {
    NewMap := make(map[string]*Struct1)
    NewMap["abc"] = &Struct1{"abc", "def", 1.0, 2.0}
    subvalMetric := "Var1"

    for _, Value:= range NewMap {
        s := reflect.ValueOf(&Value).Elem()

    // use of String() method
        println(s.String())
        println(s.Elem().String())

        metric := s.Elem().FieldByName(subvalMetric).Interface()
        fmt.Println(metric)
    }

}
```

**输出:**

```go
<*main.Struct1 Value>
<main.Struct1 Value>
abc

```