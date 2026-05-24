# 如何在 Golang 中将字符串转换为浮点类型？

> 原文:[https://www . geesforgeks . org/如何将字符串转换为浮点类型 in-golang/](https://www.geeksforgeeks.org/how-to-convert-string-to-float-type-in-golang/)

**ParseFloat** 函数是 **strconv** 库中的内置函数，它将字符串类型转换为精度由位大小指定的浮点数。

**示例:**在本例中，相同的字符串 **-2.514** 被转换为浮点数据类型，然后打印它们的总和。一旦它被转换为 8 位大小，其他时候它是 32 位大小。两者产生不同的结果，因为 ParseFloat 接受十进制和十六进制浮点数语法。如果 a1 或 a2 格式良好且接近有效的浮点数，ParseFloat 将返回使用 IEEE754 无偏舍入法舍入的最近的浮点数，该方法仅在十六进制表示中的位数超过尾数时对十六进制浮点值进行舍入。

```go
// Golang program to Convert
// string to float type
package main

import (
    "fmt"
    "strconv"
)

func main() {

    // defining a string a1
    a1 := "-2.514"

    // converting the string a1 
    // into float and storing it
    // in b1 using ParseFloat
    b1, _ := strconv.ParseFloat(a1, 8)

    // printing the float b1
    fmt.Println(b1)

    a2 := "-2.514"
    b2, _ := strconv.ParseFloat(a2, 32)
    fmt.Println(b2)

    fmt.Println(b1 + b2)
}
```

**输出:**

```go
-2.514
-2.5139999389648438
-5.027999938964843

```