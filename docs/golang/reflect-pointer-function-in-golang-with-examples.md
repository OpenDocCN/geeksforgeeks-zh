# 反映。Golang 中的指针()函数示例

> 原文:[https://www . geesforgeks . org/reflect-pointer-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-pointer-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 Pointer()** 函数用于获取 v 的值作为 uintptr。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) Pointer() uintptr
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数将 v 的值作为 uintptr 返回。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Pointer() Function 

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

    // use of Pointer() method
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
// reflect.Pointer() Function 

package main

import (
    "fmt"
    "play.ground/foo"
    "reflect"
    "unsafe"
)

func GetUnexportedField(field reflect.Value) interface{} {
    return reflect.NewAt(field.Type(), unsafe.Pointer(field.UnsafeAddr())).Elem().Interface()
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