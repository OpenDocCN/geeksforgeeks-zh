# 反映。Golang 中的 CanSet()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-can set-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-canset-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 CanSet()** 功能用于检查 v 的值是否可以更改。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) CanSet() bool
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回布尔值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.CanSet() Function

package main

import (
    "reflect"
    "fmt"

)

type ProductionInfo struct {
    StructA []Entry
}

type Entry struct {
    Field1            string
    Field2            int
}

func SetField(source interface{}, fieldName string, fieldValue string){
    v := reflect.ValueOf(source)
    tt := reflect.TypeOf(source)

    for k := 0; k < tt.NumField(); k++ {
        fieldValue := reflect.ValueOf(v.Field(k))

        // use of CanSet() method
        fmt.Println(fieldValue.CanSet())
        if fieldValue.CanSet(){
            fieldValue.SetString(fieldValue.String())
        }
    }
}

// Main function
func main() {
    source := ProductionInfo{}
    source.StructA = append(source.StructA, Entry{Field1: "A", Field2: 2})

    SetField(source, "Field1", "NEW_VALUE")
}        
```

**输出:**

```go
false

```

**例 2:**

```go
// Golang program to illustrate
// reflect.CanSet() Function

package main

import (
    "fmt"
    "reflect"
)

type ProductionInfo struct {
    StructA []Entry
}

type Entry struct {
    Field1 string
    Field2 int
}

func SetField(source interface{}, fieldName string, fieldValue string) {
    v := reflect.ValueOf(source).Elem()

    // use of CanSet() method
    fmt.Println(v.FieldByName(fieldName).CanSet())

    if v.FieldByName(fieldName).CanSet() {
        v.FieldByName(fieldName).SetString(fieldValue)
    }
}

// Main function
func main() {
    source := ProductionInfo{}
    source.StructA = append(source.StructA, Entry{Field1: "A", Field2: 2})

    fmt.Println("Before: ", source.StructA[0])
    SetField(&source.StructA[0], "Field1", "NEW_VALUE")
    fmt.Println("After: ", source.StructA[0])
}
```

**输出:**

```go
Before:  {A 2}
true
After:  {NEW_VALUE 2}

```