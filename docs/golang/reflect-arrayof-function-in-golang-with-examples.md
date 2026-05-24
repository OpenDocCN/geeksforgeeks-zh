# 反映。Golang 中的 ArrayOf()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-arrayof-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-arrayof-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 ArrayOf()** 函数用于获取给定计数和元素类型的数组类型，即如果 x 表示 int，则 ArrayOf(10，x)表示[10]int。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func ArrayOf(count int, elem Type) Type
> 
> ```
> 
> **参数:**该函数取 int 类型(计数)和 type 类型(elem)两个参数。
> 
> **返回值:**该函数返回给定计数和元素类型的数组类型。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.ArrayOf() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    // use of ArrayOf method
    ta := reflect.ArrayOf(5, reflect.TypeOf(123))
    fmt.Println(ta)
}
```

**输出:**

```go
[5]int

```

**例 2:**

```go
// Golang program to illustrate
// reflect.ArrayOf() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {
    t := reflect.TypeOf(5)

    // use of ArrayOf method
    arr := reflect.ArrayOf(4, t)
    inst := reflect.New(arr).Interface().(*[4]int)

    for i := 1; i <= 4; i++ {
        inst[i-1] = i*i
    }

    fmt.Println(inst)
}
```

**输出:**

```go
&[1 4 9 16]

```