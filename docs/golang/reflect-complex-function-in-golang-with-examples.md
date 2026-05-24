# 反映。Golang 中的复数()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-complex-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-complex-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 Complex()** 函数用于获取 v 的基础值。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) Complex() complex128
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**这个函数返回 v 的基础值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate 
// reflect.complex() Function 

package main

 import (
    "fmt"
    "reflect"
 )

 func main() {        
    fmt.Println(reflect.ValueOf(complex(0, 0)).Complex())

 }                 
```

**输出:**

```go
(0+0i)

```

**例 2:**

```go
// Golang program to illustrate 
// reflect.Complex() Function 

package main

 import (
    "fmt"
    "reflect"
 )

const a = complex(100, 8)

 const b = complex(8, 100)

 func main() {
    fmt.Println("Complex number a : ", a)
    fmt.Println("Complex number b : ", b)

    c := a + b

    fmt.Println(reflect.ValueOf(c).Complex())

 }         
```

**输出:**

```go
Complex number a :  (100+8i)
Complex number b :  (8+100i)
(108+108i)

```