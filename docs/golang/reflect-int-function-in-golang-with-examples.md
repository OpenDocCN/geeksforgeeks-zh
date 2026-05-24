# 反映。Golang 中的 Int()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-int-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-int-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。int()**Golang 中的函数用来获取 v 的基础值，作为 int64。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) Int() int64
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**这个函数返回 v 的基础值，作为 int64。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate 
// reflect.Int() Function 

package main

 import (
    "fmt"
    "reflect"
 )

 func main() {

    // use of Int() method
    fmt.Println(reflect.ValueOf(678).Int())

 } 
```

**输出:**

```go
678

```

**例 2:**

```go
// Golang program to illustrate 
// reflect.Int() Function 

package main

 import (
    "fmt"
    "reflect"
 )

const a = 2
const b = 3

 func main() {
    fmt.Println("Number a : ", a)
    fmt.Println("Number b : ", b)

    c := a + b

    // use of Int() method
    fmt.Println(reflect.ValueOf(c).Int())

 } 
```

**输出:**

```go
Number a :  2
Number b :  3
5

```