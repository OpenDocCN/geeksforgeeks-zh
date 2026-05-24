# 反映。Golang 中的 DeepEqual()函数及示例

> 原文:[https://www . geesforgeks . org/reflect-deep equal-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-deepequal-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 DeepEqual()** 函数用于检查 x 和 y 是否“深度相等”。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> func DeepEqual(x，y 接口{}) bool
> 
> **参数:**该函数取两个任意类型值的参数，即 x，y。
> **返回值:**该函数返回布尔值。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

## 去

```go
// Golang program to illustrate
// reflect.DeepEqual() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    map_1 := map[int]string{

        200: "Anita",
        201: "Neha",
        203: "Suman",
        204: "Robin",
        205: "Rohit",
    }
    map_2 := map[int]string{

        200: "Anita",
        201: "Neha",
        203: "Suman",
        204: "Robin",
        205: "Rohit",
    }

    // DeepEqual is used to check
    // two interfaces are equal or not
    res1 := reflect.DeepEqual(map_1, map_2)
    fmt.Println("Is Map 1 is equal to Map 2: ", res1)
}
```

**输出:**

```go
Is Map 1 is equal to Map 2:  true
```

**例 2:**

## 去

```go
// Golang program to illustrate
// reflect.DeepEqual() Function

package main

import (
    "fmt"
    "reflect"
)

// Main function
func main() {

    src := reflect.ValueOf([]int{10, 20, 32})
    dest := reflect.ValueOf([]int{1, 2, 3})

    cnt := reflect.Copy(dest, src)
    cnt+=1

    // DeepEqual is used to check
    // two interfaces are equal or not
    res1 := reflect.DeepEqual(src, dest )
    fmt.Println("Is dest is equal to src: ", res1)
}
```

**输出:**

```go
Is dest is equal to src:  false
```