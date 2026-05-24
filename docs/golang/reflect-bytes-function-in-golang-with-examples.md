# 反映。Golang 中的 Bytes()函数示例

> 原文:[https://www . geesforgeks . org/reflect-bytes-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-bytes-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 Bytes()** 函数用于获取值基础值。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) Bytes() []byte
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
// reflect.Bytes() Function

package main

import (
    "fmt"
    "reflect"
)

type vall[]uint8

// Main function 
func main() {

    // use of Bytes() method
    fmt.Println(reflect.ValueOf(vall{'A', 'B', 'C', 'D', 'E'}).Bytes())
}        
```

**输出:**

```go
[65 66 67 68 69]

```

**例 2:**

```go
// Golang program to illustrate
// reflect.Bytes() Function

package main

import (
    "fmt"
    "reflect"
)

type val1 uint8
type slicee []val1 

// Main function 
func main() {
    var val = slicee{11, 12, 13}

    // use of Bytes() method
    va := reflect.ValueOf(val).Bytes()
    va[1] = 4
    fmt.Println(val)
}
```

**输出:**

```go
[11 4 13]

```