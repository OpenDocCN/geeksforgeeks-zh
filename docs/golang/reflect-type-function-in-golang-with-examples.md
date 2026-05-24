# 反映。Golang 中的 Type()函数示例

> 原文:[https://www . geesforgeks . org/reflect-type-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-type-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。type()**Golang 中的函数用于获取 v 的类型。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) Type() Type
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回 v 的类型。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Type() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    var val chan int

    // use of Type() method
    value := reflect.MakeChan(reflect.Indirect(reflect.ValueOf(&val)).Type(), 0)

    fmt.Println("Value :", value)
}
```

**输出:**

```go
Value : 0xc00010c000

```

**例 2:**

```go
// Golang program to illustrate
// reflect.Type() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    var str map[int]string 

    var strValue reflect.Value = reflect.ValueOf(&str)

    indirectStr := reflect.Indirect(strValue)

    //Use of Type() method

    valueMap := reflect.MakeMap(indirectStr.Type())

    fmt.Printf("ValueMap is [%v] .", valueMap)

}
```

**输出:**

```go
ValueMap is [map[]] .

```