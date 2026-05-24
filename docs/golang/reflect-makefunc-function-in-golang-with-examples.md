# 反映。Golang 中的 MakeFunc()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-make func-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-makefunc-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 makeffunc()**函数用于获取给定类型的新函数，该函数包装函数 fn。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func MakeFunc(typ Type, fn func(args []Value) (results []Value)) Value
> 
> ```
> 
> **参数:**该函数取以下参数:
> 
> *   **类型:**该参数为类型。
> *   **fn :** 该参数为功能函数。
> 
> **返回值:**该函数返回一个给定类型的新函数，该函数包装函数 fn。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.MakeFunc() Function

package main

import (
    "fmt"
    "reflect"
)

func InvertSlice(args []reflect.Value) (result []reflect.Value) {
    inSlice, n := args[0], args[0].Len()
    outSlice := reflect.MakeSlice(inSlice.Type(), 0, n)
    for i := n-1; i >= 0; i-- {
        element := inSlice.Index(i)
        outSlice = reflect.Append(outSlice, element)
    }
    return []reflect.Value{outSlice}
}

func Bind(p interface{}, f func ([]reflect.Value) []reflect.Value) {

    invert := reflect.ValueOf(p).Elem()

    //Use of MakeFunc() method
    invert.Set(reflect.MakeFunc(invert.Type(), f))
}

// Main function
func main() {

     var invertInts func([]int) []int
    Bind(&invertInts, InvertSlice)
    fmt.Println(invertInts([]int{1, 2, 3, 4, 2, 3, 5}))

}
```

**输出:**

```go
[5 3 2 4 3 2 1]

```

**例 2:**

```go
// Golang program to illustrate
// reflect.MakeFunc() Function

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
    case reflect.Int, reflect.Int8, reflect.Int16, reflect.Int32, reflect.Int64:
        return []reflect.Value{reflect.ValueOf(a.Int() + b.Int())}
    case reflect.Uint, reflect.Uint8, reflect.Uint16, reflect.Uint32, reflect.Uint64:
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
    fmt.Println(stringSum("Geeksfor", "Geeks"))

}
```

**输出:**

```go
3
5.599999904632568
GeeksforGeeks

```