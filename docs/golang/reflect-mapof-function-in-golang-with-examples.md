# 反映。Golang 中的 MapOf()函数示例

> 原文:[https://www . geesforgeks . org/reflect-mapof-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-mapof-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 MapOf()** 函数用于获取给定键和元素类型的映射类型，即如果 k 代表 int，e 代表 string，则 MapOf(k，e)代表 map[int]string。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func MapOf(key, elem Type) Type
> 
> ```
> 
> **参数:**该函数取 Type 类型的三个参数(key，elem)。
> 
> **返回值:**该函数返回给定键和元素类型的映射类型。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.MapOf() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    var i interface{}

    // use of MapOf method
    tm := reflect.MapOf(reflect.TypeOf("string"),
                      reflect.TypeOf(&i).Elem())

    fmt.Println(tm)
}
```

**输出:**

```go
map[string]interface {}

```

**例 2:**

```go
// Golang program to illustrate
// reflect.MapOf() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    ta := reflect.ArrayOf(5, reflect.TypeOf(123))

    tc := reflect.ChanOf(reflect.SendDir, ta)

    //use of MapOf method
    tm := reflect.MapOf(ta, tc)

    fmt.Println(tm)
}
```

**输出:**

```go
map[[5]int]chan<- [5]int

```