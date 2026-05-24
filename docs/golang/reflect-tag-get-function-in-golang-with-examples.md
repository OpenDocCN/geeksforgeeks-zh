# 反映。用例子标记 Golang 中的 Get()函数

> 原文:[https://www . geesforgeks . org/reflect-tag-get-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-tag-get-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。tag . Get()**Golang 中的函数用于查找标签字符串中与 key 相关联的值，如果标签中没有这样的 key，则返回一个空字符串。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (tag StructTag) Get(key string) string
> 
> ```
> 
> **参数:**该函数取一个字符串类型的参数，即 key。
> 
> **返回值:**该函数返回与标记字符串中的键相关联的值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Tag.Get() Function

package main

import (
    "fmt"
    "reflect"
)

type Employee struct {
    ID      string `auto_increment:"true" increment:"1"`
    Name    string `varchar: "255"`
    Surname string `"varchar: "255"`
}

// Main function
func main() {
    e := Employee{}
    // c variable represents table columns
    c := reflect.TypeOf(e).Field(0).Tag
    fmt.Printf("%s\n\n", c)

    // use of Get method
    g := c.Get("increment")
    fmt.Printf("Get method: %s\n", g)
}
```

**输出:**

```go
auto_increment:"true" increment:"1"

Get method: 1

```

**例 2:**

```go
// Golang program to illustrate
// reflect.Tag.Get() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {
    type tag struct {
        val string `Value_1:"GeeksforGeeks" Value_2:"Best Platform :"`
    }

    src := tag {}
    st := reflect.TypeOf(src)
    field := st.Field(0)

    // use of Get method
    fmt.Println(field.Tag.Get("Value_2"), field.Tag.Get("Value_1"))

}
```

**输出:**

```go
Best Platform : GeeksforGeeks

```