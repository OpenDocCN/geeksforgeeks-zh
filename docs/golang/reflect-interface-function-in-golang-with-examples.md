# 反映。Golang 中的 Interface()函数示例

> 原文:[https://www . geesforgeks . org/reflect-interface-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-interface-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 Interface()** 函数用于获取 v 的当前值作为接口{}。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) Interface() (i interface{})
> 
> ```
> 
> **参数:**该函数只接受一个参数。
> 
> *   **i :** 该参数为接口{}类型
> 
> **返回值:**这个函数返回 v 的当前值作为接口{}。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Interface() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {
    t := reflect.TypeOf(5)

    //use of Interface method
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
// reflect.Interface() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    var str []string
    var v reflect.Value = reflect.ValueOf(&str)

    v = v.Elem()

    v = reflect.Append(v, reflect.ValueOf("a"))
    v = reflect.Append(v, reflect.ValueOf("b"))
    v = reflect.Append(v, reflect.ValueOf("c"), reflect.ValueOf("j, k, l"))

    fmt.Println("Our value is a type of :", v.Kind())

    vSlice := v.Slice(0, v.Len())
    vSliceElems := vSlice.Interface()

    fmt.Println("With the elements of : ", vSliceElems)

}
```

**输出:**

```go
Our value is a type of : slice
With the elements of :  [a b c j, k, l]

```