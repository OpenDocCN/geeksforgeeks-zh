# 反映。用例子复制 Golang 中的()函数

> 原文:[https://www . geesforgeks . org/reflect-copy-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-copy-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。copy()**Golang 中的函数用于将源的内容复制到目的地，直到目的地已满或源已用尽。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func Copy(dst, src Value) int
> 
> ```
> 
> **参数:**该函数取切片或数组类型的两个参数。dst 和 src 必须具有相同的元素类型。
> 
> **返回值:**此函数返回复制的元素数量。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Copy() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    // Source 
    src := reflect.ValueOf([]int{10, 20, 32})

    /* make sure the dest space is larger than src */
    // destination 
    dest := reflect.ValueOf([]int{1, 2, 3})

    // To copy Copy() function is used
    // and it returns the number of 
    // elements copied
    cnt := reflect.Copy(dest, src)
    data := dest.Interface().([]int)
    data[0] = 100

    // printing the values
    fmt.Println("Number of element Copied :", cnt)
    fmt.Println("Source :", src)
    fmt.Println("destination :", dest)
}
```

**输出:**

```go
Number of element Copied : 3
Source : [10 20 32]
destination : [100 20 32]

```

**例 2:**

```go
// Golang program to illustrate
// reflect.Copy() Function 

package main

import (
    "fmt"
    "reflect"
)

// Struct with two int value
type temp struct {
    A0 []int
    A1 []int
}

// Main function 
func main() {

    var val temp

    // Source 
    val.A0 = append(val.A0, []int{1, 2, 3,
                    4, 5, 6, 7, 8, 9}...)

    // destination 
    val.A1 = append(val.A1, 9, 8, 7, 6)

    // To copy Copy() function is used
    // and it returns the number of 
    // elements copied
    var n = reflect.Copy(reflect.ValueOf(val.A0), 
                        reflect.ValueOf(val.A1))

    // printing the values
    fmt.Println("Number of element Copied :", n)
    fmt.Println("{Source, destination} :", val)

}
```

**输出:**

```go
Number of element Copied : 4
{Source, destination} : {[9 8 7 6 5 6 7 8 9] [9 8 7 6]}

```