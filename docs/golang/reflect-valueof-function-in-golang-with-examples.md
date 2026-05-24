# 反映。Golang 中的 ValueOf()函数示例

> 原文:[https://www . geesforgeks . org/reflect-value of-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-valueof-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 ValueOf()** 函数用于将新值初始化为接口 I 中存储的具体值，要访问该函数，需要在程序中导入 reflect 包。

> **语法:**
> 
> ```go
> func ValueOf(i interface{}) Value
> 
> ```
> 
> **参数:**该函数取以下参数:
> 
> *   **i:** 此参数为接口。
> 
> **返回值:**该函数返回初始化为接口 I 中存储的具体值的新值

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.ValueOf() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    a := []int{2, 5}

    var b reflect.Value = reflect.ValueOf(&a)

    b = b.Elem()

    fmt.Println("Slice :", a)

    //use of ValueOf method

    b = reflect.Append(b, reflect.ValueOf(80))
    fmt.Println("Slice after appending data:", b)

}        
```

**输出:**

```go
Slice : [2 5]
Slice after appending data: [2 5 80]

```

**例 2:**

```go
// Golang program to illustrate
// reflect.ValueOf() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    src := reflect.ValueOf([]int{10, 20, 32})

    dest := reflect.ValueOf([]int{1, 2, 3})

    // use of ValueOf() method
    fmt.Println(src, dest)
}
```

**输出:**

```go
[10 20 32] [1 2 3]

```