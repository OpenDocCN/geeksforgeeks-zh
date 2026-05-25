# Golang 中的零值

> Original: [https://www.geeksforgeeks.org/zero-value-in-golang/](https://www.geeksforgeeks.org/zero-value-in-golang/)

在 GO 语言中，每当我们通过声明或使用 `new` 为变量分配内存时，如果变量没有显式初始化，那么这类[变量](https://www.geeksforgeeks.org/go-variables/)的值就会自动用它们的零值初始化。零值的初始化是递归完成的。因此，如果没有使用任何值指定结构的[数组](https://www.geeksforgeeks.org/arrays-in-go/)的每个元素，那么它们的字段都为零。以下是不同类型变量的零值：

| 类型 | 零值 |
| :--- | :--- |
| 整数 | `0` |
| 浮点数 | `0.0` |
| 布尔 | `false` |
| 字符串 | `""` |
| 指针 | `nil` |
| 接口 | `nil` |
| 切片 | `nil` |
| 映射 | `nil` |
| 通道 | `nil` |
| 函数 | `nil` |

## 示例 1

```go
// Go program to illustrate the concept of zero value
package main

import "fmt"

// Main Method
func main() {

    // Creating variables
    // of different types
    var q1 int
    var q2 float64
    var q3 bool
    var q4 string
    var q5 []int
    var q6 *int
    var q7 map[int]string

    // Displaying the zero value
    // of the above variables
    fmt.Println("Zero value for integer types: ", q1)
    fmt.Println("Zero value for float64 types: ", q2)
    fmt.Println("Zero value for boolean types: ", q3)
    fmt.Println("Zero value for string types: ", q4)
    fmt.Println("Zero value for slice types: ", q5)
    fmt.Println("Zero value for pointer types: ", q6)
    fmt.Println("Zero value for map types: ", q7)
}
```

输出：

```go
Zero value for integer types:  0
Zero value for float64 types:  0
Zero value for boolean types:  false
Zero value for string types:  
Zero value for slice types:  []
Zero value for pointer types:  <nil>
Zero value for map types:  map[]
```

## 示例 2

```go
// Go program to check the variable
// contains zero value or not
package main

import "fmt"

func main() {

    // Creating variables of different types
    var q1 int = 2
    var q2 float64
    var q3 bool
    var q4 string

    // Slice
    var q5 []int

    // Pointer
    var q6 *int

    // Map
    var q7 map[int]string

    // Checking if the given variables
    // contain their zero value or not
    if q1 == 0 {
        fmt.Println("True")
    } else {
        fmt.Println("False")
    }

    if q2 == 0 {
        fmt.Println("True")
    } else {
        fmt.Println("False")
    }

    if q3 == false {
        fmt.Println("True")
    } else {
        fmt.Println("False")
    }

    if q4 == "" {
        fmt.Println("True")
    } else {
        fmt.Println("False")
    }

    if q5 == nil {
        fmt.Println("True")
    } else {
        fmt.Println("False")
    }

    if q6 == nil {
        fmt.Println("True")
    } else {
        fmt.Println("False")
    }

    if q7 == nil {
        fmt.Println("True")
    } else {
        fmt.Println("False")
    }
}
```

输出：

```go
False
True
True
True
True
True
True
```