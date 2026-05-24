# 反映。Golang 中的新()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-new-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-new-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 New()** 函数用于获取表示指向指定类型的新零值的指针的值。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func New(typ Type) Value
> 
> ```
> 
> **参数:**该函数取以下参数:
> 
> *   **类型:**该参数为类型。
> 
> **返回值:**该函数返回一个值，该值表示指向指定类型的新零值的指针。

以下示例说明了上述方法在 Golang 中的使用:
**示例 1:**

```go
// Golang program to illustrate
// reflect.New() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {
    t := reflect.TypeOf(5)

    //use of ArrayOf method
    arr := reflect.ArrayOf(4, t)
    inst := reflect.New(arr).Interface().(*[4]int)

    for i := 1; i <= 4; i++ {
        inst[i-1] = i*i
    }

    fmt.Println(inst)
}
```

**输出:**

```go
&[1 4 9 16]

```

**例 2:**

```go
// Golang program to illustrate
// reflect.New() Function 

package main

import (
    "fmt"
    "reflect"
)

type Geek struct {
    A int `tag1:"First Tag" tag2:"Second Tag"`
    B string
}

// Main function
func main() {
    greeting := "GeeksforGeeks"
    f := Geek{A: 10, B: "Number"}

    gVal := reflect.ValueOf(greeting)

    fmt.Println(gVal.Interface())

    gpVal := reflect.ValueOf(&greeting)
    gpVal.Elem().SetString("Articles")
    fmt.Println(greeting)

    fType := reflect.TypeOf(f)
    fVal := reflect.New(fType)
    fVal.Elem().Field(0).SetInt(20)
    fVal.Elem().Field(1).SetString("Number")
    f2 := fVal.Elem().Interface().(Geek)
    fmt.Printf("%+v, %d, %s\n", f2, f2.A, f2.B)
}
```

**输出:**

```go
GeeksforGeeks
Articles
{A:20 B:Number}, 20, Number

```