# 反映。Golang 中的 Float()函数示例

> 原文:[https://www . geesforgeks . org/reflect-float-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-float-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 Float()** 函数用于获取 v 的基础值，作为 float64。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) Float() float64
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**这个函数返回 v 的基础值，如 float64。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate 
// reflect.Float() Function 

package main

 import (
    "fmt"
    "reflect"
 )

 func main() {   

    fmt.Println(reflect.ValueOf(1.2).Float())

 }       
```

**输出:**

```go
1.2

```

**例 2:**

```go
// Golang program to illustrate 
// reflect.Float() Function 

package main

 import (
    "fmt"
    "reflect"
 )

const a = 1.2

const b = 3

 func main() {
    fmt.Println("Number a : ", a)
    fmt.Println("Number b : ", b)

    c := a + b

    // use of Float() method
    fmt.Println(reflect.ValueOf(c).Float())

 } 
```

**输出:**

```go
Number a :  1.2
Number b :  3
4.2

```