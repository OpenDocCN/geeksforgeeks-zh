# 反映。用例子调用 Golang 中的()函数

> 原文:[https://www . geesforgeks . org/reflect-call-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-call-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 Call()** 函数用于调用带有中输入参数的函数 v。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) Call(in []Value) []Value
> 
> ```
> 
> **参数:**该函数取以下参数:
> 
> *   中的**该参数为[]值类型。**
> 
> **返回值:**该函数将输出结果作为值返回。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Call() Function

package main

import "fmt"
import "reflect"

type T struct {}

func (t *T) Geeks() {
    fmt.Println("GeekforGeeks")
}

func main() {
    var t T

    // use of Call() method
    val := reflect.ValueOf(&t).MethodByName("Geeks").Call([]reflect.Value{})

    fmt.Println(val)
}        
```

**输出:**

```go
GeekforGeeks
[]

```

**例 2:**

```go
// Golang program to illustrate
// reflect.Call() Function

package main

import "fmt"
import "reflect"

type T struct {}

func (t *T) Geeks() {
    fmt.Println("GeekforGeeks")
}

func (t *T) Geeks1() {
    fmt.Println("Golang Package :")
    fmt.Println("reflect")
    fmt.Println("Call() Function")    
}

func main() {
    var t T
    var t1 T
    // use of Call() method
    reflect.ValueOf(&t).MethodByName("Geeks").Call([]reflect.Value{})

    reflect.ValueOf(&t1).MethodByName("Geeks1").Call([]reflect.Value{})

} 
```

**输出:**

```go
GeekforGeeks
Golang Package :
reflect
Call() Function

```