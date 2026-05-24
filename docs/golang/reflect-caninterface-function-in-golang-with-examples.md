# 反映。Golang 中的 CanInterface()函数示例

> 原文:[https://www . geesforgeks . org/reflect-caninterface-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-caninterface-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 canadar()**功能用于检查 Interface 是否可以使用而不会出现死机。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) CanInterface() bool
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
// reflect.CanInterface() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function  
func main() {

    num := 6
    meta := reflect.ValueOf(num)

    // use of CanInterface() method
    fmt.Println("canInterface:", meta.CanInterface() == true)
}        
```

**输出:**

```go
canInterface: true

```

**例 2:**

```go
// Golang program to illustrate
// reflect.CanInterface() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function  
func main() {

    string := "ABC"
    meta := reflect.ValueOf(&string)

    // use of CanInterface() method
    fmt.Println("canInterface:", meta.CanInterface() == false)
}
```

**输出:**

```go
canInterface: false

```