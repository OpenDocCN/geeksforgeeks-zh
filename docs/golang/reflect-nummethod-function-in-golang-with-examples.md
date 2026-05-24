# 反映。Golang 中的 NumMethod()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-nummethod-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-nummethod-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 NumMethod()** 函数用于获取值的方法集中导出的方法数量。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) NumMethod() int
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回值的方法集中导出的方法数。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.NumMethod() Function 

package main

import (
    "fmt"
    "reflect"
)

type gfg struct {
    Prop string
}

func (f gfg) Geek1() string {
    return f.Prop
}

func (f gfg) Geek2() {
}

// Main function 
func main() {
    fooType := reflect.TypeOf(gfg{})
    for i := 0; i < fooType.NumMethod(); i++ {
        method := fooType.Method(i)
        fmt.Println(method.Name)
    }
}
```

**输出:**

```go
Geek1
Geek2

```

**例 2:**

```go
// Golang program to illustrate
// reflect.NumMethod() Function 

package main

import (
    "log"
    "reflect"
)

type Reindeer string

func (r Reindeer) TakeOff() {
    log.Printf("%q lifts off.", r)
}

func (r Reindeer) Land() {
    log.Printf("%q gently lands.", r)
}

func (r Reindeer) ToggleNose() {
    if r != "rudolph" {
        panic("invalid reindeer operation")
    }
    log.Printf("%q nose changes state.", r)
}

func main() {
    r := Reindeer("rudolph")

    t := reflect.TypeOf(r)

    for i := 0; i < t.NumMethod(); i++ {
        m := t.Method(i)
        log.Printf("%s", m.Name)
    }
}
```

**输出:**

```go
2009/11/10 23:00:00 Land
2009/11/10 23:00:00 TakeOff
2009/11/10 23:00:00 ToggleNose

```