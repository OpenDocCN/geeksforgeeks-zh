# 反映。函数()函数在 Golang 中的应用举例

> 原文:[https://www . geesforgeks . org/reflect-fun of-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-funcof-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 FuncOf()** 函数用于获取给定参数和结果类型的函数类型，即如果 k 代表 int，e 代表 string，则 FuncOf([]Type{k}，[]Type{e}，false)代表 func(int) string。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func FuncOf(in, out []Type, variadic bool) Type
> 
> ```
> 
> **参数:**该函数取[]类型(输入、输出)和布尔类型(变量)三个参数。
> 
> **返回值:**该函数返回给定参数和结果类型的函数类型。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.FuncOf() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    ta := reflect.ArrayOf(5, reflect.TypeOf(123))

    tc := reflect.ChanOf(reflect.SendDir, ta)

    tp := reflect.PtrTo(ta)

    // use of FuncOf method
    tf := reflect.FuncOf([]reflect.Type{ta},
             []reflect.Type{tp, tc}, false)
    fmt.Println(tf)
}
```

**输出:**

```go
func([5]int) (*[5]int, chan<- [5]int)

```

**例 2:**

```go
// Golang program to illustrate
// reflect.FuncOf() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    var k = reflect.TypeOf(0)
    var e = reflect.TypeOf("")

    // use of FuncOf method
    fmt.Println(reflect.FuncOf([]reflect.Type{k},
             []reflect.Type{e}, false).String())
}
```

**输出:**

```go
func(int) string

```