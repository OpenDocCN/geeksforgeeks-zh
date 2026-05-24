# 使用多个返回值的 Golang 程序

> 原文:[https://www . geesforgeks . org/golang-使用多个返回值的程序/](https://www.geeksforgeeks.org/golang-program-that-uses-multiple-return-values/)

在 Golang 中，我们可以从单个函数中*一次返回多个值*。通过在函数签名中更改函数的返回类型，可以获得多个返回值。

**语法:**

```go
func value( ) ( int , int ) { 
return 1 , 0 ; 
} 
```

这个函数签名中的(int，int)解释了返回类型是两个整数。因此，我们在调用这个函数时必须使用多个赋值。该功能也用于从函数返回*结果和错误*。如果您想要返回值的*子集，请使用空白标识符 **_** 。*

**示例 1:** 找到两个元素的最大值和最小值，使用此功能:

## Go

```go
package main

import "fmt"

// declaring a function
// having return type
// of int, int
func maxmin(a int, b int) (int, int) {

    if a > b {

        // separate multiple return
        // values using comma
        return a, b
    } else {

        return b, a
    }
    // this function returns
    // maximum , minimum values
}

func main() {

    // declaring two values a and b
    var a = 50
    var b = 70

    // calling the function
    // with multiple assignments
    var max, min = maxmin(a, b)

    // Printing the values
    fmt.Println("Max = ", max, "\nMin = ", min)
}
```