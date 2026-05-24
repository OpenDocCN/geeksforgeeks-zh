# 反映。Golang 中的 TypeOf()函数示例

> 原文:[https://www . geesforgeks . org/reflect-type-of-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-typeof-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 TypeOf()** 函数用于获取代表 I 动态类型的反射类型，要访问该函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func TypeOf(i interface{}) Type
> 
> ```
> 
> **参数:**该函数只取接口(I)的一个参数。
> 
> **返回值:**该函数返回反射类型。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.TypeOf() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    tst1 := "string"
    tst2 := 10
    tst3 := 1.2
    tst4 := true
    tst5 := []string{"foo", "bar", "baz"}
    tst6 := map[string]int{"apple": 23, "tomato": 13}

    // use of TypeOf method       
    fmt.Println(reflect.TypeOf(tst1))   
    fmt.Println(reflect.TypeOf(tst2))
    fmt.Println(reflect.TypeOf(tst3))
    fmt.Println(reflect.TypeOf(tst4))
    fmt.Println(reflect.TypeOf(tst5))
    fmt.Println(reflect.TypeOf(tst6))

}
```

**输出:**

```go
string
int
float64
bool
[]string
map[string]int

```

**例 2:**

```go
// Golang program to illustrate
// reflect.TypeOf() Function 

package main

import (
    "fmt"
    "io"
    "os"
    "reflect"
)

// Main function
func main() {

    // use of TypeOf method
    tt := reflect.TypeOf((*io.Writer)(nil)).Elem()

    fileType := reflect.TypeOf((*os.File)(nil))
    fmt.Println(fileType.Implements(tt))

}
```

**输出:**

```go
true

```