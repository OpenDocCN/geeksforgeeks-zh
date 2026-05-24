# 在 Golang 中将字符串变量转换为布尔、整数或浮点类型

> 原文:[https://www . geesforgeks . org/将字符串变量转换为布尔整数或浮点类型 in-golang/](https://www.geeksforgeeks.org/converting-a-string-variable-into-boolean-integer-or-float-type-in-golang/)

在 Golang 中执行任务时需要各种类型的字符串转换。导入程序包 **strconv** 以执行字符串之间的转换。

### 字符串到布尔的转换

ParseBool 用于将字符串转换为布尔值。它接受 1，T，T，真，真，真作为**真**，0，F，F，假，假，假作为**假**。任何其他值都会返回一个错误，并将该值显示为 false。

**示例:**

```go
// Golang program to convert a string
// into Boolean data type

package main

import (
    "fmt"
    "reflect"
    "strconv"
)

func main() {

    str := "GeeksforGeeks"

    fmt.Println("Before :", reflect.TypeOf(str))
    fmt.Println("String value is: ", str)
    b, _ := strconv.ParseBool(str)
    fmt.Println("After :", reflect.TypeOf(b))
    fmt.Println("Boolean value is: ", b, "\n")

    str1 := "t"

    fmt.Println("Before :", reflect.TypeOf(str1))
    fmt.Println("String value is: ", str1)
    b1, _ := strconv.ParseBool(str1)
    fmt.Println("After :", reflect.TypeOf(b1))
    fmt.Println("Boolean value is: ", b1, "\n")

    str2 := "0"

    fmt.Println("Before :", reflect.TypeOf(str2))
    fmt.Println("String value is: ", str2)
    b2, _ := strconv.ParseBool(str2)
    fmt.Println("After :", reflect.TypeOf(b2))
    fmt.Println("Boolean value is: ", b2, "\n")

}
```

**输出:**

```go
Before : string
String value is:  GeeksforGeeks
After : bool
Boolean value is:  false 

Before : string
String value is:  t
After : bool
Boolean value is:  true 

Before : string
String value is:  0
After : bool
Boolean value is:  false 

```

### 字符串到整数的转换

ParseInt 函数用于将字符串转换为整数值。它解释给定基数(0，2 到 36)和位大小(0 到 64)的字符串，并返回相应的值。

**示例:**

```go
// Golang program to convert String 
// into Integer Data type
package main

import (
    "fmt"
    "reflect"
    "strconv"
)

func main() {

    str := "GeeksforGeeks"

    fmt.Println("Before :", reflect.TypeOf(str))
    fmt.Println("String value is: ", str)
    i, _ := strconv.ParseInt(str, 10, 64)
    fmt.Println("After :", reflect.TypeOf(i))
    fmt.Println("Integer value is: ", i, "\n")

    str1 := "100"

    fmt.Println("Before :", reflect.TypeOf(str1))
    fmt.Println("String value is: ", str1)
    i1, _ := strconv.ParseInt(str1, 10, 64)
    fmt.Println("After :", reflect.TypeOf(i1))
    fmt.Println("Integer value is: ", i1, "\n")

}
```

**输出:**

```go
Before : string
String value is:  GeeksforGeeks
After : int64
Integer value is:  0 

Before : string
String value is:  100
After : int64
Integer value is:  100 

```

### 字符串到浮点的转换

ParseFloat 用于将字符串转换为浮点类型，精度由 bitSize 指定:float32 为 32，float64 为 64。当 bitSize=32 时，结果仍然有类型 float64，但它将转换为 float32，而不改变其值。

**示例:**

```go
// Golang program to convert
// String into Float Data type
package main

import (
    "fmt"
    "reflect"
    "strconv"
)

func main() {

    str := "3.1415926535"

    fmt.Println("Before :", reflect.TypeOf(str))
    fmt.Println("String value is: ", str)
    f, _ := strconv.ParseFloat(str, 64)
    fmt.Println("After :", reflect.TypeOf(f))
    fmt.Println("Float value is: ", f, "\n")

    str1 := "3.1415926535"

    fmt.Println("Before :", reflect.TypeOf(str1))
    fmt.Println("String value is: ", str1)
    f1, _ := strconv.ParseFloat(str1, 32)
    fmt.Println("After :", reflect.TypeOf(f1))
    fmt.Println("Float value is: ", f1, "\n")

}
```

**输出:**

```go
Before : string
String value is:  3.1415926535
After : float64
Float value is:  3.1415926535 

Before : string
String value is:  3.1415926535
After : float64
Float value is:  3.1415927410125732 

```