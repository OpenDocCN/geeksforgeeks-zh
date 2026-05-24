# 反映。Golang 中的 StructOf()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-structof-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-structof-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 structure of()**函数用于获取包含字段的结构类型。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func StructOf(fields []StructField) Type
> 
> ```
> 
> **参数:**该函数只取 StructFields(字段)的一个参数。
> 
> **返回值:**该函数返回包含字段的结构类型。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.SliceOf() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    // use of StructOf method
    typ := reflect.StructOf([]reflect.StructField{
        {
            Name: "Height",
            Type: reflect.TypeOf(float64(0)),
        },
        {
            Name: "Name",
            Type: reflect.TypeOf("abc"),
        },
    })

    fmt.Println(typ)

}
```

**输出:**

```go
struct { Height float64; Name string }

```

**例 2:**

```go
// Golang program to illustrate
// reflect.SliceOf() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    // use of StructOf method
    tt:= reflect.StructOf([]reflect.StructField{
        {
            Name: "Height",
            Type: reflect.TypeOf(0.0),
            Tag:  `json:"height"`,
        },
        {
            Name: "Name",
            Type: reflect.TypeOf("abc"),
            Tag:  `json:"name"`,
        },
    })

    fmt.Println(tt.NumField()) 
    fmt.Println(tt.Field(0))
    fmt.Println(tt.Field(1))

}
```

**输出:**

```go
2
{Height  float64 json:"height" 0 [0] false}
{Name  string json:"name" 8 [1] false}

```