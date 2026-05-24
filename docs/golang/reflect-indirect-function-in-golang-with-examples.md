# 反映。Golang 中的间接()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-间接-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-indirect-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的间接()**函数用于获取 v 指向的值，即如果 v 是一个零指针，间接返回一个零值。如果 v 不是指针，间接返回 v。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func Indirect(v Value) Value
> 
> ```
> 
> **参数:**该函数取以下参数:
> 
> *   **v:** 此参数是要传递的值。
> 
> **返回值:**该函数返回 v 指向的值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Indirect() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {
     val1:= []int  {1, 2, 3, 4}             

     var val2 reflect.Value = reflect.ValueOf(&val1)
     fmt.Println("&val2 type : ", val2.Kind())

     // using the function
     indirectI := reflect.Indirect(val2)
     fmt.Println("indirectI  type : ", indirectI.Kind())
     fmt.Println("indirectI  value : ", indirectI)

}
```

**输出:**

```go
&val2 type :  ptr
indirectI  type :  slice
indirectI  value :  [1 2 3 4]

```

**例 2:**

```go
// Golang program to illustrate
// reflect.Indirect() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {
     var val1 []int               
     var val2 [3]string        
     var val3 = make(map[int]string) 

     var val4 reflect.Value = reflect.ValueOf(&val1)
     indirectI := reflect.Indirect(val4)
     fmt.Println("val1: ", indirectI.Kind())

     var val5 reflect.Value = reflect.ValueOf(&val2)
     indirectStr := reflect.Indirect(val5)
     fmt.Println("val2 type : ", indirectStr.Kind())

     var val6 reflect.Value = reflect.ValueOf(&val3)
     fmt.Println("&val3 type : ", val6.Kind())

     indirectM := reflect.Indirect(val6)
     fmt.Println("val3 type : ", indirectM.Kind())

}
```

**输出:**

```go
val1:  slice
val2 type :  array
&val3 type :  ptr
val3 type :  map

```