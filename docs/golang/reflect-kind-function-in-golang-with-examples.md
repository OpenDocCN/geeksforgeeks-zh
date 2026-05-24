# 反映。Golang 中的 Kind()函数示例

> 原文:[https://www . geesforgeks . org/reflect-kind-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-kind-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 Kind()** 函数用于查找 Kind 的名称。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (k Kind) String() string
> 
> ```
> 
> **参数:**该函数不取任何参数。
> 
> **返回值:**该函数返回字符串(种类名称)。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Kind() Function

package main

import (
    "fmt"
    "reflect"
)

type temp struct {
    ord int
    cId int
}

// function to use the
// Kind() method
func useKind(val interface{}) {
    s1 := reflect.TypeOf(val)

    // Kind() function is used
    // to find the kind
    s2 := s1.Kind()
    fmt.Println("Type ", s1)
    fmt.Println("Kind ", s2)

}

// Main function
func main() {
    val := temp{
        ord: 1,
        cId: 513,
    }
    useKind(val)

}
```

**输出:**

```go
Type  main.temp
Kind  struct

```

**例 2:**

```go
// Golang program to illustrate
// reflect.Kind() Function

package main

import (
    "fmt"
    "reflect"
)

type temp struct {
    ord int
    cId int
}

// function to use the
// Kind() method
func useKind(val interface{}) {

    // Kind() function is used
    // to find the kind
    if reflect.ValueOf(val).Kind() == reflect.Struct {
        v := reflect.ValueOf(val)
        fmt.Println("Number of fields", v.NumField())
        for i := 0; i < v.NumField(); i++ {
            fmt.Printf("Field: %d \t type: %T \t value: %v\n",
                                    i, v.Field(i), v.Field(i))
        }
    }

}

// Main function
func main() {
    val := temp{
        ord: 1,
        cId: 513,
    }
    useKind(val)

}
```

**输出:**

```go
Number of fields 2
Field: 0      type: reflect.Value      value: 1
Field: 1      type: reflect.Value      value: 513

```