# 反映。Golang 中的 SetBool()函数示例

> 原文:[https://www . geesforgeks . org/reflect-setbool-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-setbool-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 SetBool()** 函数用于设置 v 的基础值。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) SetBool(x bool)
> 
> ```
> 
> **参数:**该函数接受布尔类型(x)的一个参数。
> 
> **返回值:**该函数不返回值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.SetBool() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    typ := reflect.StructOf([]reflect.StructField{
        {
            Name: "Height",
            Type: reflect.TypeOf(bool(true)),
            Tag:  `json:"height"`,
        },
        {
            Name: "Age",
            Type: reflect.TypeOf(int(0)),
            Tag:  `json:"age"`,
        },
    })

    v := reflect.New(typ).Elem()
    v.Field(0).SetBool(true)
    fmt.Println(v)
}
```

**输出:**

```go
{true 0}

```

**例 2:**

```go
// Golang program to illustrate
// reflect.SetBool() Function 

package main

import (
    "fmt"
    "reflect"
)

type Foo struct {
    A int `tag1:"First Tag" tag2:"Second Tag"`
    B string
    C bool
}

func main() {
    greeting := "ABC"
    f := Foo{A: 10, B: "Geek1", C:true}

    gVal := reflect.ValueOf(greeting)
    fmt.Println(gVal.Interface())

    gpVal := reflect.ValueOf(&greeting)
    gpVal.Elem().SetString("Geek2")
    fmt.Println(greeting)

    fType := reflect.TypeOf(f)
    fVal := reflect.New(fType)
    fVal.Elem().Field(0).SetInt(20)
    fVal.Elem().Field(1).SetString("Geeksforgeeks")
    fVal.Elem().Field(2).SetBool(false)
    f2 := fVal.Elem().Interface().(Foo)
    fmt.Printf("%+v, %d, %s, %+v\n", f2, f2.A, f2.B, f2.C)
}
```

**输出:**

```go
ABC
Geek2
{A:20 B:Geeksforgeeks C:false}, 20, Geeksforgeeks, false

```