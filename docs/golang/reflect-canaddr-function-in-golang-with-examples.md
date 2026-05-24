# 反映。Golang 中的 CanAddr()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-canadar-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-canaddr-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 canadar()**函数用于检查是否可以用 Addr 获取值的地址。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) CanAddr() bool
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回布尔值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.CanAddr() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    typ := reflect.StructOf([]reflect.StructField{
        {
            Name: "Height",
            Type: reflect.TypeOf(float64(0)),
            Tag:  `json:"height"`,
        },
        {
            Name: "Age",
            Type: reflect.TypeOf(int(0)),
            Tag:  `json:"age"`,
        },
    })

    v := reflect.New(typ).Elem()
    v.Field(0).SetFloat(0.4)
    v.Field(1).SetInt(2)
    s := v.CanAddr()
    fmt.Printf("value: %+v\n", s)
}         
```

**输出:**

```go
value: true

```

**例 2:**

```go
// Golang program to illustrate
// reflect.CanAddr() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function 
type superint struct {
    A int
    B int
}

func (s *superint) lol() {}

type a interface{ lol() }

func main() {
    i := superint{A: 1, B: 9}
    valPtr := reflect.ValueOf(&i)
    fmt.Printf("%v \n", i)

    // use of Addr() method
    fmt.Printf("%v \n", valPtr.Elem().CanAddr())
}
```

**输出:**

```go
{1 9} 
true 

```