# 反映。Golang 中的 IsValid()函数，示例

> 原文:[https://www . geesforgeks . org/reflect-is valid-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-isvalid-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 IsValid()** 函数用于检查 v 是否表示值。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) IsValid() bool
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**这个函数返回 v 是否代表一个值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.IsValid() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    // Use of IsValid() method
    fmt.Println(reflect.Value{}.IsValid())
    fmt.Println(reflect.ValueOf(nil).IsValid())
}
```

**输出:**

```go
false
false

```

**例 2:**

```go
// Golang program to illustrate
// reflect.IsValid() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {
    var i *int
    v := reflect.ValueOf(i)
    v2 := v.Elem()

    // Use of IsValid() method
    fmt.Println(v2.IsValid())
    fmt.Println(reflect.ValueOf(nil).IsValid())

    fmt.Println(reflect.Indirect(v).IsValid())

}
```

**输出:**

```go
false
false
false

```