# 反映。Golang 中的 FieldByIndex()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-field by index-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-fieldbyindex-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。利用 Golang 中的 FieldByIndex()** 函数获取索引对应的嵌套字段。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) FieldByIndex(index []int) Value
> 
> ```
> 
> **参数:**该函数只接受单个参数。
> 
> *   **索引:**此参数为[]int 类型。
> 
> **返回值:**该函数返回索引对应的嵌套字段。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.FieldByIndex() Function 

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

    // use of FieldByIndex() method
    fmt.Println(tt.FieldByIndex([]int{0}))

}    
```

**输出:**

```go
{Height  float64 json:"height" 0 [0] false}

```

**例 2:**

```go
// Golang program to illustrate
// reflect.FieldByIndex() Function 

package main

import (
    "fmt"
    "reflect"
)

type User struct {
    Id   int
    Name string
    Age  int
}

type Manager struct {
         User 
    Title string
}

// Main function 
func main() {

    m := Manager{User: User{1, "Jack", 12}, Title: "123"}
    t := reflect.TypeOf(m)
         fmt.Printf("%#v\n", t.Field(0)) 
    fmt.Printf("%#v \n", t.Field(1))

    // use of FieldByIndex() method
    fmt.Printf("%#v \n", t.FieldByIndex([]int{0, 0}))
    fmt.Printf("%#v \n", t.FieldByIndex([]int{0, 1}))
    fmt.Printf("%#v \n", t.FieldByIndex([]int{0, 2}))

}
```

**输出:**

> 反思。structure field { Name:“User”，PkgPath:“”，Type:(*reflect.rtype)(0x4b1480)，Tag:“”，偏移量:0x0，Index:[]int{0}，Anonymous:true}
> reflect。structure field { Name:“Title”，PkgPath:“”，Type:(*reflect.rtype)(0x4a1c20)，Tag:“”，Offset:0x20，Index:[]int{1}，Anonymous:false}
> reflect。structure field { Name:“Id”，PkgPath:“”，Type:(*reflect.rtype)(0x4a14e0)，Tag:“”，Offset:0x0，Index:[]int{0}，Anonymous:false}
> reflect。structure field { Name:“Name”，PkgPath:“”，Type:(*reflect.rtype)(0x4a1c20)，Tag:“”，Offset:0x8，Index:[]int{1}，Anonymous:false}
> reflect。structure field { Name:“Age”，PkgPath:“”，Type:(*reflect.rtype)(0x4a14e0)，标记:“”，偏移量:0x18，索引:[]int{2}，匿名:false}