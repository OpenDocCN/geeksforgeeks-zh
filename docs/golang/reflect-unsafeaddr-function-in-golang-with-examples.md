# 反映。Golang 中的 UnsafeAddr()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-unsafedr-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-unsafeaddr-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 unsafeadr()**函数用来获取 v 的数据指针。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) UnsafeAddr() uintptr
> ```
> 
> **参数:**此功能不接受任何参数。
> **返回值:**这个函数返回 v 的数据指针。

以下示例说明了上述方法在 Golang 中的使用:
**示例 1:**

## C

```go
// Golang program to illustrate
// reflect.UnsafeAddr() Function

package main

import (
    "fmt"
    "reflect"
    "unsafe"
)

// Main function
func main() {
        var s = struct{ foo int }{42}
    var i int

    rs := reflect.ValueOf(&s).Elem()
    rf := rs.Field(0)               
    ri := reflect.ValueOf(&i).Elem()

    rf = reflect.NewAt(rf.Type(), unsafe.Pointer(rf.UnsafeAddr())).Elem()
    ri.Set(rf)
    rf.Set(ri)
    fmt.Println(rf)
    fmt.Println(ri)

}
```