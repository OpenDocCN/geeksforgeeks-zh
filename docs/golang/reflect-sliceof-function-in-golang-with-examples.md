# 反映。Golang 中的 SliceOf()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-sliceof-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-sliceof-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 SliceOf()** 函数用于获取元素类型为 t 的切片类型，即如果 t 表示 int，则 SliceOf(t)表示[]int。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func SliceOf(t Type) Type
> 
> ```
> 
> **参数:**该函数只取 Type 类型(t)的一个参数。
> 
> **返回值:**该函数返回元素类型为 t 的切片类型

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

    v := reflect.TypeOf("123")

    // use of SliceOfmethod
    fmt.Println(reflect.SliceOf(v))

}
```

**输出:**

```go
[]string

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

    ta := reflect.ArrayOf( 10, reflect.TypeOf("123"))

    tc := reflect.ChanOf(reflect.SendDir, ta)

    tp := reflect.PtrTo(tc)

    ts := reflect.SliceOf(tp)

    // use of SliceOf method
    fmt.Println(ts)

}
```

**输出:**

```go
[]*chan<- [10]string

```