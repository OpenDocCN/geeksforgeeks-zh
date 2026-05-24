# 反映。Golang 中的 MapKeys()函数示例

> 原文:[https://www . geesforgeks . org/reflect-mapkeys-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-mapkeys-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 MapKeys()** 函数用于获取包含地图中存在的所有关键点的切片，顺序未指定。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) MapKeys() []Value
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回包含地图中所有关键点的切片，顺序未指定。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.MapKeys() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {
    key := 10
    value := "Geeksforgeeks"

    mapType := reflect.MapOf(reflect.TypeOf(key), reflect.TypeOf(value))

    mapValue := reflect.MakeMap(mapType)
    mapValue.SetMapIndex(reflect.ValueOf(key), reflect.ValueOf(value))

    keys := mapValue.MapKeys()
    fmt.Println(keys)

}
```

**输出:**

```go
[<int Value>]

```

**例 2:**

```go
// Golang program to illustrate
// reflect.MapKeys() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {
    key := 1
    value := "abc"

    mapType := reflect.MapOf(reflect.TypeOf(key), reflect.TypeOf(value))

    mapValue := reflect.MakeMap(mapType)
    mapValue.SetMapIndex(reflect.ValueOf(key), reflect.ValueOf(value))
    mapValue.SetMapIndex(reflect.ValueOf(2), reflect.ValueOf("def"))
    mapValue.SetMapIndex(reflect.ValueOf(3), reflect.ValueOf("gh"))

    keys := mapValue.MapKeys()
    for _, k := range keys {
        c_key := k.Convert(mapValue.Type().Key())
        c_value := mapValue.MapIndex(c_key)
        fmt.Println("key :", c_key, " value:", c_value)
    }

}
```

**输出:**

```go
key : 1  value: abc
key : 2  value: def
key : 3  value: gh

```