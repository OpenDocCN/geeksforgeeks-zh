# 反映。Golang 中的 MakeMap()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-make map-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-makemap-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 MakeMap()** 函数用于创建指定类型的新地图。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func MakeMap(typ Type) Value
> 
> ```
> 
> **参数:**该函数取以下参数:
> 
> *   **类型:**该参数为类型。
> 
> **返回值:**这个函数返回一个新创建的地图。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.MakeMap() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    var str map[int]string 

     var strValue reflect.Value = reflect.ValueOf(&str)

     indirectStr := reflect.Indirect(strValue)

    //Use of MakeMap() method

     valueMap := reflect.MakeMap(indirectStr.Type())

     fmt.Printf("ValueMap is [%v] .", valueMap)

}
```

**输出:**

```go
ValueMap is [map[]] .

```

**例 2:**

```go
// Golang program to illustrate
// reflect.MakeMap() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    intSlice := make([]int, 0)
    mapStringInt := make(map[string]int)

    sliceType := reflect.TypeOf(intSlice)
    mapType := reflect.TypeOf(mapStringInt)

    intSliceReflect := reflect.MakeSlice(sliceType, 0, 0)
    mapReflect := reflect.MakeMap(mapType)

    v := 100
    rv := reflect.ValueOf(v)
    intSliceReflect = reflect.Append(intSliceReflect, rv)
    intSlice2 := intSliceReflect.Interface().([]int)
    fmt.Println(intSlice2)

    k := "GeeksforGeeks"
    rk := reflect.ValueOf(k)
    mapReflect.SetMapIndex(rk, rv)
    mapStringInt2 := mapReflect.Interface().(map[string]int)
    fmt.Println(mapStringInt2)

}
```

**输出:**

```go
[100]
map[GeeksforGeeks:100]

```