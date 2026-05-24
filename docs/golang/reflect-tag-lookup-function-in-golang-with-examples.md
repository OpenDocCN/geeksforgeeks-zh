# 反映。Golang 中的 Tag.Lookup()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-tag-lookup-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-tag-lookup-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。tag . Lookup()**Golang 中的函数用于查找标签字符串中与 key 相关联的值，如果标签中没有这样的 key，则返回空字符串，并确定标签是否被显式设置为空字符串。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (tag StructTag) Lookup(key string) (value string, ok bool)
> 
> ```
> 
> **参数:**该函数取字符串类型(值)和 bool 类型(ok)两个参数。
> 
> **返回值:**该函数返回与标记字符串中的键相关联的值，该值是显式设置的。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Tag.Lookup() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {
    type S struct {
        F0 string `val:"123456"`
        F1 string `val:""`
        F2 string
    }

    s := S{}
    st := reflect.TypeOf(s)
    for i := 0; i < st.NumField(); i++ {
        field := st.Field(i)

        // use of Lookup method
        if value, ok := field.Tag.Lookup("val"); ok {
            if value == "" {
                fmt.Println("(Empty)")
            } else {
                fmt.Println(value)
            }
        } else {
            fmt.Println("(Non specific)")
        }
    }    
}
```

**输出:**

```go
123456
(Empty)
(Non specific)

```

**例 2:**

```go
// Golang program to illustrate
// reflect.Tag.Lookup() Function 

package main

import (
    "fmt"
    "reflect"
    "strconv"
)

type Temp struct {
    ID string `auto_increment:"true" increment:"1"`
    Name string `varchar: "255"`
    Surname string `"varchar: "255"`
}

// Main function 
func main() {
    v:= Temp{}
    // c variable represents table columns
    c := reflect.TypeOf(v).Field(0).Tag

    // g variable represents get
    g := c.Get("increment")
    fmt.Printf("Get method: %s\n", g)

    val, ok := c.Lookup("auto_increments")
    fmt.Printf("Lookup method: %s- %s", val, strconv.FormatBool(ok))    
}
```

**输出:**

```go
Get method: 1
Lookup method: - false

```