# 反映。用例子在 Golang 中设置()函数

> 原文:[https://www . geesforgeks . org/reflect-set-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-set-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 Set()** 函数用于将 x 赋给值 v。要访问该函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) Set(x Value)
> 
> ```
> 
> **参数:**该函数接受值类型(x)的一个参数。
> 
> **返回值:**该函数不返回值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate 
// reflect.Set() Function 

package main 

import ( 
    "fmt"
    "reflect"
    "unsafe"
) 

// Main function 
func main() {
        var s = struct{ foo int }{654}
    var i int

    rs := reflect.ValueOf(&s).Elem() 
    rf := rs.Field(0)                
    ri := reflect.ValueOf(&i).Elem() 

    rf = reflect.NewAt(rf.Type(), unsafe.Pointer(rf.UnsafeAddr())).Elem()
    ri.Set(rf)
    rf.Set(ri)
    fmt.Println(rf) 
    fmt.Println(ri) 

}
```

**输出:**

```go
654
654

```

**例 2:**

```go
// Golang program to illustrate
// reflect.Set() Function

package main

import (
    "fmt"
    "reflect"
)

func sum(args []reflect.Value) []reflect.Value {
    a, b := args[0], args[1]
    if a.Kind() != b.Kind() {
        fmt.Println("??? ????.")
        return nil
    }

    switch a.Kind() {
    case reflect.Int, reflect.Int8, reflect.Int16,
                     reflect.Int32, reflect.Int64:
        return []reflect.Value{reflect.ValueOf(a.Int() + b.Int())}

    case reflect.Uint, reflect.Uint8, reflect.Uint16, 
                      reflect.Uint32, reflect.Uint64:
        return []reflect.Value{reflect.ValueOf(a.Uint() + b.Uint())}

    case reflect.Float32, reflect.Float64:
        return []reflect.Value{reflect.ValueOf(a.Float() + b.Float())}

    case reflect.String:
        return []reflect.Value{reflect.ValueOf(a.String() + b.String())}

    default:
        return []reflect.Value{}
    }
}

func makeSum(fptr interface{}) {
    fn := reflect.ValueOf(fptr).Elem()

    v := reflect.MakeFunc(fn.Type(), sum)

    fn.Set(v)
}

// Main function
func main() {

    var stringSum func(string, string) string

    makeSum(&stringSum)

    fmt.Println(stringSum("Value_1 : ", "Geeks_1"))

}
```

**输出:**

```go
Value_1 : Geeks_1

```