# 反映。Golang 中的 Uint()函数示例

> 原文:[https://www . geesforgeks . org/reflect-uint-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-uint-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 Uint()** 函数用于获取 v 的基础值，作为 uint64。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) Uint() uint64
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**这个函数返回 v 的基础值，作为 uint64。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Uint() Function

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

    var intSum func(int, int) int64
    var floatSum func(float32, float32) float64
    var stringSum func(string, string) string

    makeSum(&intSum)
    makeSum(&floatSum)
    makeSum(&stringSum)

    fmt.Println(intSum(1, 2))
    fmt.Println(floatSum(2.1, 3.5))
    fmt.Println(stringSum("Geeksfor","Geeks"))

}
```

**输出:**

```go
3
5.599999904632568
GeeksforGeeks

```

**例 2:**

```go
// Golang program to illustrate
// reflect.Uint() Function

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

    fmt.Println(stringSum("Value_1 : ","Geeks_1"))

}
```

**输出:**

```go
Value_1 : Geeks_1

```