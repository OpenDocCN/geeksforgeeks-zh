# Golang 中的 strcom.atoi()函数，示例

> Original: [https://www.geeksforgeeks.org/strconv-atoi-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strconv-atoi-function-in-golang-with-examples/)

Go 语言提供内置支持，通过 strconv 包实现基本数据类型的字符串表示形式之间的转换。 此包提供了一个**atoi()函数**，该函数相当于 ParseInt(str string，base int，bitSize int)用于将字符串类型转换为 int 类型。 要访问**atoi()函数**，您需要在程序中导入 strconv 包。

**语法：**

```go
func Atoi(str string) (int, error)
```

这里，str 是字符串。

**示例 1：**

```go
// Golang program to illustrate
// strconv.Atoi() function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Using Atoi() function
    x := "245"
    y, e := strconv.Atoi(x)
    if e == nil {
        fmt.Printf("%T \n %v", y, y)
    }

}
```

发帖主题：Re：Колибри0.7.0

```go
int 
 245

```

**示例 2：**

```go
// Golang program to illustrate
// strconv.Atoi() function
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // Using Atoi() function
    x1 := "245"
    fmt.Println("Before:")
    fmt.Printf("Type: %T ", x1)
    fmt.Printf("\nValue: %v", x1)
    y1, e1 := strconv.Atoi(x1)
    if e1 == nil {
        fmt.Println("\nAfter:")
        fmt.Printf("Type: %T ", y1)
        fmt.Printf("\nValue: %v", y1)
    }

    x2 := "1"
    fmt.Println("\n\nBefore:")
    fmt.Printf("Type: %T ", x2)
    fmt.Printf("\nValue: %v", x2)
    y2, e2 := strconv.Atoi(x2)
    if e2 == nil {
        fmt.Println("\nAfter:")
        fmt.Printf("Type: %T ", y2)
        fmt.Printf("\nValue: %v", y2)
    }

}
```

发帖主题：Re：Колибри0.7.0

```go
Before:
Type: string 
Value: 245
After:
Type: int 
Value: 245

Before:
Type: string 
Value: 1
After:
Type: int 
Value: 1

```