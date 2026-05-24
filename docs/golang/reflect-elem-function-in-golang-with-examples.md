# 反映。Elem()函数在 Golang 中的应用示例

> 原文:[https://www . geesforgeks . org/reflect-elem-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-elem-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 Elem()** 函数用于获取接口 v 包含的或者指针 v 指向的值。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) Elem() Value
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回接口 v 包含的值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Elem() Function

package main

import (
    "fmt"
    "reflect"

)
type Book struct {
    Id    int   
    Title string
    Price float32
    Authors []string    
}

// Main function   
func main() {
    book := Book{}

    //use of Elem() method
    e := reflect.ValueOf(&book).Elem()

    for i := 0; i < e.NumField(); i++ {
        varName := e.Type().Field(i).Name
        varType := e.Type().Field(i).Type
        varValue := e.Field(i).Interface()
        fmt.Printf("%v %v %v\n", varName, varType, varValue)
    }
}        
```

**输出:**

```go
Id int 0
Title string 
Price float32 0
Authors []string []

```

**例 2:**

```go
// Golang program to illustrate
// reflect.Elem() Function

package main

import (
    "fmt"
    "reflect"
     "io"
     "os"     
)

// Main function   
func main() {

    //use of Elem() method
    writerType := reflect.TypeOf((*io.Writer)(nil)).Elem()

    fileType := reflect.TypeOf((*os.File)(nil))
    fmt.Println(fileType.Implements(writerType))
}     
```

**输出:**

```go
true

```