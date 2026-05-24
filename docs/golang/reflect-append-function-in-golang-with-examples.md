# 反映。用例子在 Golang 中追加()函数

> 原文:[https://www . geesforgeks . org/reflect-append-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-append-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。append()**Golang 中的函数用于将值 x 追加到一个片 s 中，要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func Append(s Value, x ...Value) Value
> 
> ```
> 
> **参数:**该函数取以下参数:
> 
> *   **s:** 此参数是要追加值的切片。
> *   **x:** 这些参数是要追加值。
> 
> **返回值:**该函数返回结果切片。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Append() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    a := []int{2, 5}

    var b reflect.Value = reflect.ValueOf(&a)

    b = b.Elem()

    fmt.Println("Slice :", a)

    // use of Append method

    b = reflect.Append(b, reflect.ValueOf(80))
    fmt.Println("Slice after appending data:", b)

}
```

**输出:**

```go
Slice : [2 5]
Slice after appending data: [2 5 80]

```

**例 2:**

```go
// Golang program to illustrate
// reflect.Append() Function

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

     // using the function
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