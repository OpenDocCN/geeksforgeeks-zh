# 反映。Golang 中的 FieldByName()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-field by name-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-fieldbyname-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 FieldByName()** 函数用于获取给定名称的结构字段。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) FieldByName(name string) Value
> 
> ```
> 
> **参数:**该函数只接受单个参数。
> 
> *   **名称:**该参数为字符串类型。
> 
> **返回值:**该函数返回给定名称的结构字段。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.FieldByName() Function 

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
        println(s.String())
        println(s.Elem().String())

        // use of FieldByName() method
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

**例 2:**

```go
// Golang program to illustrate
// reflect.FieldByName() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {
    type t struct {
            N int
    }
    var n = t{76}
    fmt.Println(n.N)

    // use of FieldByName() method
    reflect.ValueOf(&n).Elem().FieldByName("N").SetInt(4)
    fmt.Println(n.N)    
}
```

**输出:**

```go
76
4

```