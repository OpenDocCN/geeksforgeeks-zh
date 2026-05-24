# 反映。Golang 中的 NewAt()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-newat-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-newat-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 NewAt()** 函数用于获取表示指向指定类型值的指针的 Value，使用 p 作为该指针。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func NewAt(typ Type, p unsafe.Pointer) Value
> 
> ```
> 
> **参数:**该函数取以下参数:
> 
> *   **类型:**该参数为类型。
> *   **p :** 该参数为不安全指针。
> 
> **返回值:**该函数返回一个值，该值表示指向指定类型值的指针。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.NewAt() Function 

package main

import (
    "reflect"
    "unsafe"
    "fmt"
)

func main() {
    var s = struct{ foo int }{100}
    var i int

    rs := reflect.ValueOf(&s).Elem() 
    rf := rs.Field(0)              
    ri := reflect.ValueOf(&i).Elem()

    // use of NewAt() method
    rf = reflect.NewAt(rf.Type(), unsafe.Pointer(rf.UnsafeAddr())).Elem()
    ri.Set(rf)
    rf.Set(ri)

    fmt.Println(rf)
}
```

**输出:**

```go
100

```

**例 2:**

```go
// Golang program to illustrate
// reflect.NewAt() Function 

package main

import (
    "fmt"
    "play.ground/foo"
    "reflect"
    "unsafe"
)

func GetUnexportedField(field reflect.Value) interface{} {
    return reflect.NewAt(field.Type(), 
      unsafe.Pointer(field.UnsafeAddr())).Elem().Interface()
}

func SetUnexportedField(field reflect.Value, value interface{}) {
    reflect.NewAt(field.Type(), unsafe.Pointer(field.UnsafeAddr())).
        Elem().
        Set(reflect.ValueOf(value))
}

func main() {
    f := &foo.Foo{
        Exported: "Old Value ",
    }

    fmt.Println(f.Exported) 

    field := reflect.ValueOf(f).Elem().FieldByName("unexported")
    SetUnexportedField(field, "New Value")
    fmt.Println(GetUnexportedField(field))
}

-- go.mod --
module play.ground

-- foo/foo.go --
package foo

type Foo struct {
    Exported   string
    unexported string
}
```

**输出:**

```go
Old Value 
New Value

```