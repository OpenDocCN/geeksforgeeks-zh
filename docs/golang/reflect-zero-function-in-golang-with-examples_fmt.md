# Go语言reflect包中的Zero()函数详解

> 原文：[https://www.geeksforgeeks.org/reflect-zero-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-zero-function-in-golang-with-examples/)

Go语言提供了运行时反射的内置支持实现，并允许程序在`reflect`包的帮助下操作任意类型的对象。`reflect.Zero()`函数用于获取表示指定类型的零值的`Value`。要访问这个函数，需要在程序中导入`reflect`包。

## 语法

```go
func Zero(typ Type) Value
```

**参数：** 该函数取以下参数：
*   `typ`：该参数为`Type`类型。

**返回值：** 该函数返回代表指定类型零值的`Value`。

以下示例说明了上述方法在Golang中的使用：

## 示例

### 例 1

```go
// Golang program to illustrate
// reflect.Zero() Function

package main

import (
    "fmt"
    "reflect"
)

func main() {
    s := struct{ A int }{0}
    field := reflect.ValueOf(s).Field(0)

    fmt.Println(field.Interface())

    // use of Zero() method
    fmt.Println(reflect.Zero(field.Type()))

    fmt.Println(reflect.DeepEqual(field.Interface(), reflect.Zero(field.Type())))
}
```

**输出：**

```go
0
0
false
```

### 例 2

```go
// Golang program to illustrate
// reflect.Zero() Function

package main

import (
    "fmt"
    "reflect"
)

func main() {
    s := struct{ A int }{0}
    field := reflect.ValueOf(s).Field(0)

    fmt.Println(field.Interface())

    // use of Zero() method
    fmt.Println(reflect.Zero(field.Type()))
    fmt.Println(reflect.TypeOf(field.Interface()))

    // use of Zero() method
    fmt.Println(reflect.TypeOf(reflect.Zero(field.Type())))

    // use of Zero() method
    fmt.Println(reflect.DeepEqual(field.Interface(),
        reflect.Zero(field.Type())))

    fmt.Println(reflect.DeepEqual(field.Interface(),
        int(reflect.Zero(field.Type()).Int())))
    fmt.Println(reflect.DeepEqual(s, struct{ A int }{}))
    fmt.Println(reflect.DeepEqual(s, struct{ A int }{0}))
}
```

**输出：**

```go
0
int
reflect.Value
false
true
true
true
```