# 反映。Golang 中的 Swapper()函数示例

> 原文:[https://www . geesforgeks . org/reflect-swapper-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-swapper-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 Swapper()** 函数用于交换所提供切片中的元素。要访问这个函数，需要在程序中导入反射包。

> **语法:**
> 
> ```go
> func Swapper(slice interface{}) func(i, j int)
> 
> ```
> 
> **参数:**该函数取一个切片类型的参数。
> 
> **返回值:**该函数返回交换的切片。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```go
// Golang program to illustrate
// reflect.Swapper() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    // Slice 
    src := []int{1, 2, 3, 4, 5}

    fmt.Printf("Before swap: %v\n", src)

    // Swapper() function is used
    // to swaps the elements in 
    // the provided slice
    swapF := reflect.Swapper(src) 

    swapF(2, 4)

    // printing the values
    fmt.Printf("After swap: %v\n", src)
}
```

**输出:**

```go
Before swap: [1 2 3 4 5]
After swap: [1 2 5 4 3]

```

**示例 2:** 使用 **Swapper()** 功能反转切片

```go
// Golang program to illustrate
// reflect.Swapper() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    // Slice 
    src := []int{1, 2, 3, 4, 5, 6, 7}

    fmt.Printf("Original Slice: %v\n", src)

    // Swapper() function is used
    // to swaps the elements in 
    // the provided slice
    swapF := reflect.Swapper(src)

    for i := 0; i < len(src)/2; i++ {
        swapF(i, len(src)-1-i)
    }

    // printing the values
    fmt.Printf("Reversed Slice: %v\n", src)
}
```

**输出:**

```go
Original Slice: [1 2 3 4 5 6 7]
Reversed Slice: [7 6 5 4 3 2 1]

```

**示例 3:** 使用 **Swapper()** 功能对切片进行排序

```go
// Golang program to illustrate
// reflect.Swapper() Function 

package main

import (
    "fmt"
    "reflect"
)

// Main function 
func main() {

    // Slice 
    src := []int{1, 2, 6, 3, 8, 0, 7, 9, 5, 4, 42, 1, 3, 4, 3}

    fmt.Printf("Original Slice: %v\n", src)

    // Swapper() function is used
    // to swaps the elements in 
    //the provided slice
    swapF := reflect.Swapper(src)

    for i := 0; i < len(src)-1; i++ {
        for j := i + 1; j < len(src); j++ {
            if src[i] > src[j] {
                swapF(i, j)
            }
        }
    }

    //printing the values
    fmt.Printf("Sorted Slice: %v\n", src)
}
```

**输出:**

```go
Original Slice: [1 2 6 3 8 0 7 9 5 4 42 1 3 4 3]
Sorted Slice: [0 1 1 2 3 3 3 4 4 5 6 7 8 9 42]

```