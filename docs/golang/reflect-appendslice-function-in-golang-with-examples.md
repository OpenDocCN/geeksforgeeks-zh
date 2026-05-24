# 反映。Golang 中的 AppendSlice()函数示例

> 原文:[https://www . geesforgeks . org/reflect-appendslice-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-appendslice-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 AppendSlice()** 函数用于将一个切片 t 追加到一个切片 s 中，要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func AppendSlice(s, t Value) Value
> 
> ```
> 
> **参数:**该函数取以下参数:
> 
> *   **s:** 此参数为切片。
> *   **t:** 这个参数也是一个另外的切片。
> 
> **返回值:**该函数返回结果切片。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.AppendSlice() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    val1:= reflect.ValueOf([]int{1, 2, 3, 4, 5})

    val2:= reflect.ValueOf([]int{11, 12, 13, 14, 15})

    fmt.Println("First Slice :", val1)
    fmt.Println("Second Slice :", val1)

    val1 = reflect.AppendSlice(val1, val2)

     fmt.Println("Resultant Slice :", val1)

}
```

**输出:**

```go
First Slice : [1 2 3 4 5]
Second Slice : [1 2 3 4 5]
Resultant Slice : [1 2 3 4 5 11 12 13 14 15]

```

**例 2:**

```go
// Golang program to illustrate
// reflect.AppendSlice() Function

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

    x:= []string{"m", "p", "s"}

    fmt.Println("First Slice :", v)
    fmt.Println("Second Slice :", x)
    v = reflect.AppendSlice(v, reflect.ValueOf(x))

     fmt.Println("Resultant Slice :", v)

}
```

**输出:**

```go
First Slice : [a b c j, k, l]
Second Slice : [m p s]
Resultant Slice : [a b c j, k, l m p s]

```