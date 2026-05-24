# 反映。示例中的 PtrTo()函数

> 原文:[https://www . geesforgeks . org/reflect-ptrto-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-ptrto-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 PtrTo()** 函数用于获取带有元素 t 的指针类型，即 t 代表类型 Geek，PtrTo(t)代表*Geek。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func PtrTo(t Type) Type
> 
> ```
> 
> **参数:**该函数只取 Type 类型(t)的一个参数。
> 
> **返回值:**该函数返回元素为 t 的指针类型

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.PtrTo() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    ta := reflect.ArrayOf(5, reflect.TypeOf(123))

    // use of PtrTo method
    tp := reflect.PtrTo(ta)

    fmt.Println(tp)
}
```

**输出:**

```go
*[5]int

```

**例 2:**

```go
// Golang program to illustrate
// reflect.PtrTo() Function 

package main

import (
    "fmt"
    "reflect"

)

// Main function 
func main() {

    v := reflect.TypeOf("123")

    // use of PtrTo method
    fmt.Println(reflect.PtrTo(v))

}
```

**输出:**

```go
*string

```