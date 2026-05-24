# 反映。Golang 中的 MakeChan()函数示例

> 原文:[https://www . geesforgeks . org/reflect-make chan-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-makechan-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 MakeChan()** 函数用于创建指定类型和缓冲区大小的新通道。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func MakeChan(typ Type, buffer int) Value
> 
> ```
> 
> **参数:**该函数只取 Type 类型(typ)和 int 类型(buffer)两个参数。
> 
> **返回值:**该函数返回新创建的通道。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.MakeChan() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    var val chan int

     // create new channel
     value := reflect.MakeChan(reflect.Indirect(reflect.ValueOf(&val)).Type(), 0)

     fmt.Println("Value :", value)
}
```

**输出:**

```go
Value : 0xc00005e060

```

**例 2:**

```go
// Golang program to illustrate
// reflect.MakeChan() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    var val chan string 

     var strVal reflect.Value = reflect.ValueOf(&val)

     indirectStr := reflect.Indirect(strVal)

     // create new channel
     value := reflect.MakeChan(indirectStr.Type(), 1024)

     fmt.Printf("Type : [%v] \nCapacity : [%v]", value.Kind(), value.Cap())
}
```

**输出:**

```go
Type : [chan] 
Capacity : [1024]

```