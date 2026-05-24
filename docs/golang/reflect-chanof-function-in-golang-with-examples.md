# 反映。Golang 中的 ChanOf()函数示例

> 原文:[https://www . geesforgeks . org/reflect-chanof-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-chanof-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 ChanOf()** 函数用于获取给定方向和元素类型的通道类型，即 t 代表 int，ChanOf(RecvDir，t)代表< -chan int。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func ChanOf(dir ChanDir, t Type) Type
> 
> ```
> 
> **参数:**该函数取 ChanDir 类型(Dir)和 type 类型(t)三个参数。
> 
> **返回值:**该函数返回给定方向和元素类型的函数类型。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.ChanOf() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    var k = reflect.TypeOf(0)

    // use of ChanOf method
    fmt.Println( reflect.ChanOf(reflect.SendDir, k))
}
```

**输出:**

```go
chan<- int

```

**例 2:**

```go
// Golang program to illustrate
// reflect.ChanOf() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    ta := reflect.ArrayOf(5, reflect.TypeOf(123))

    //use of ChanOf method
    tc := reflect.ChanOf(reflect.SendDir, ta)

    fmt.Println(tc)
}
```

**输出:**

```go
chan<- [5]int

```