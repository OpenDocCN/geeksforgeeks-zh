# 位。Golang 中的 Mul()函数示例

> 原文:[https://www . geesforgeks . org/bits-mul-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-mul-function-in-golang-with-examples/)

**位。Golang 中的 Mul()函数**用于求 x 和 y 的全幅乘积，该函数的执行时间不依赖于输入。要访问这个函数，需要在程序中导入数学/位包。

**语法:**

```go
func Mul(x, y uint) (hi, lo uint)
```

**参数:**该函数取 uint 类型的两个参数，即 x，y。

**注:** (hi，lo) = x * y
这里，hi 是乘积位的上半部分，lo 是返回的下半部分。

**返回值:**此函数返回 x 和 y 的全角乘积。

**例 1:**

```go
// Golang program to illustrate
// bits.Mul() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using Mul() function
    hi, lo := bits.Mul(5, 10)
    fmt.Println("Full-width product of x and y : ", hi, lo)

}
```

**输出:**

```go
Full-width product of x and y :  0 50
```

**例 2:**

```go
// Golang program to illustrate 
// bits.Mul() Function 
package main 

import ( 
    "fmt"
    "math/bits"
) 

// Main function 
func main() { 

    // Using Mul() function 
    const a, b = 34, 56
    hi, lo  := bits.Mul(a, b) 
    fmt.Println("Number 1:", a) 
    fmt.Println("Number 2:", b) 
    fmt.Println("Upper half:", hi) 
    fmt.Println("Lower half:", lo)  

}
```

**输出:**

```go
Number 1: 34
Number 2: 56
Upper half: 0
Lower half: 1904

```