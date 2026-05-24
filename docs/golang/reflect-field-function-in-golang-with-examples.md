# 反映。Golang 中的 Field()函数示例

> 原文:[https://www . geesforgeks . org/reflect-field-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-field-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 Field()** 函数用于获取结构的第 I 个字段，要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) Field(i int) Value
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回结构的第 I 个字段

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Field() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

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

    //use of Field() method
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

**例 2:**

```go
// Golang program to illustrate
// reflect.Field() Function 

package main

import (
    "fmt"
    "reflect"
)

type temp struct {  
    ord      int
    cId int
}

// function to use the 
// Field() method 
func useKind(val interface{}) {  

    // Kind() function is used
    // to find the kind
    if reflect.ValueOf(val ).Kind() == reflect.Struct {
        v := reflect.ValueOf(val )
        fmt.Println("Number of fields", v.NumField())
        for i := 0; i < v.NumField(); i++ {
            fmt.Printf("Field: %d \t type: %T \t value: %v\n",
                                    i, v.Field(i), v.Field(i))
        }
    }

}

// Main function 
func main() {  
    val := temp {
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