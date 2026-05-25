# Go语言中的`reflect.Bool()`函数示例

> 原文：[https://www.geeksforgeeks.org/reflect-bool-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-bool-function-in-golang-with-examples/)

Go语言提供了运行时反射的内置支持实现，并允许程序在`reflect`包的帮助下操作任意类型的对象。`reflect.Bool()`函数用于获取`Value`的基础值。要访问这个函数，需要在程序中导入`reflect`包。

## 语法

```go
func (v Value) Bool() bool
```

**参数：** 此功能不接受任何参数。

**返回值：** 这个函数返回`v`的基础值。

以下示例说明了上述方法在Golang中的使用：

## 例1

```go
// Golang program to illustrate
// reflect.Bool() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function

func main() {
    v := reflect.ValueOf(true)

    // use of Bool() method
    fmt.Printf("%v \n", v.Bool())
}
```

**输出：**

```go
true
```

## 例2

```go
// Golang program to illustrate
// reflect.Bool() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function

func main() {
    v := reflect.ValueOf(false)

    // use of Bool() method
    if v.Bool() == false {
        fmt.Printf("ValueOf(false).Bool() = false")
    }
}
```

**输出：**

```go
ValueOf(false).Bool() = false
```