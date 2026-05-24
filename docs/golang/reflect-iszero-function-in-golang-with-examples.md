# 反映。Golang 中的 IsZero()函数示例

> 原文:[https://www . geesforgeks . org/reflect-is zero-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-iszero-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 IsZero()** 函数用于检查 v 是否是其类型的零值。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) IsZero() bool
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回 v 是否是其类型的零值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.IsZero() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    s := struct{ A int }{0}
    field := reflect.ValueOf(s).Field(0)

    // Use of IsZero() method
    fmt.Println(field.IsZero())
}
```

**输出:**

```go
true

```

**例 2:**

```go
// Golang program to illustrate
// reflect.IsZero() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    s := struct{ A int }{1}
    field := reflect.ValueOf(s).Field(0)

    // Use of IsZero() method
    fmt.Println(field.IsZero())
}
```

**输出:**

```go
false

```