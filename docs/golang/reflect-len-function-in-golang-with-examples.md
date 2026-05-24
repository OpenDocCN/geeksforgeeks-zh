# 反映。Len()函数在 Golang 中的应用示例

> 原文:[https://www . geesforgeks . org/reflect-len-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-len-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。len()**Golang 中的函数用于获取 v 的长度。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func (v Value) Len() int
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**这个函数返回 v 的长度

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate 
// reflect.Len() Function 

package main

 import (
    "fmt"
    "reflect"
 )

func main() {
    c := make(chan int, 1)
    vc := reflect.ValueOf(c)

    succeeded := vc.TrySend(reflect.ValueOf(123))

    // use of Len() method
    fmt.Println(succeeded, vc.Len(), vc.Cap())

} 
```

**输出:**

```go
true 1 1

```

**例 2:**

```go
// Golang program to illustrate 
// reflect.Len() Function 

package main 

import ( 
    "fmt"
    "reflect"
) 

func main() {
    data := []string{"Geeks1", "Geeks2", "Geeks3"}
    test(data)
    data1 := []int{1, 2, 3}
    test(data1)
}

func test(t interface{}) {
    switch reflect.TypeOf(t).Kind() {
    case reflect.Slice:
        s := reflect.ValueOf(t)

        for i := 0; i < s.Len(); i++ {
            fmt.Println(s.Index(i))
        }
    }
}
```

**输出:**

```go
Geeks1
Geeks2
Geeks3
1
2
3

```