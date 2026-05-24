# 反映。Golang 中的 Index()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-index-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-index-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 Index()** 函数用于获取 v 的第 I 个元素。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) Index(i int) Value
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**这个函数返回 v 的第 I 个元素。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate 
// reflect.Index() Function 

package main 

import ( 
    "fmt"
    "reflect"
) 

func main() {
    data := []string{"Geeks1", "Geeks2", "Geeks3"}
    test(data)
    data1 := []int{1, 2, 3}
    test(data1)
}

func test(t interface{}) {
    switch reflect.TypeOf(t).Kind() {
    case reflect.Slice:
        s := reflect.ValueOf(t)

        for i := 0; i < s.Len(); i++ {
            fmt.Println(s.Index(i))
        }
    }
}
```

**输出:**

```go
Geeks1
Geeks2
Geeks3
1
2
3

```

**例 2:**

```go
// Golang program to illustrate 
// reflect.Index() Function 

package main

import (
    "fmt"
    "reflect"
)

func InvertSlice(args []reflect.Value) (result []reflect.Value) {
    inSlice, n := args[0], args[0].Len()
    outSlice := reflect.MakeSlice(inSlice.Type(), 0, n)
    for i := n-1; i >= 0; i-- {

    //Use of Index() method
        element := inSlice.Index(i)
        outSlice = reflect.Append(outSlice, element)
    }
    return []reflect.Value{outSlice}
}

func Bind(p interface{}, f func ([]reflect.Value) []reflect.Value) {

    invert := reflect.ValueOf(p).Elem()
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