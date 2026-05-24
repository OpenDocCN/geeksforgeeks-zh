# 位。Mul32()在 Golang 中的作用及实例

> 原文:[https://www . geesforgeks . org/bits-mul 32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-mul32-function-in-golang-with-examples/)

**位。Golang 中的 Mul32()函数**用来求 x 和 y 的 64 位乘积，这个函数的执行时间不依赖于输入。要访问这个函数，需要在程序中导入数学/位包。

**语法:**

```go
func Mul32(x, y uint32) (hi, lo uint32)

```

**参数:**该函数取 uint32 类型的两个参数，即 x，y。

**注:** (hi，lo) = x * y
这里，hi 是乘积位的上半部分，lo 是返回的下半部分。

**返回值:**该函数返回 x 和 y 的 **64 位乘积**

**例 1:**

```go
// Golang program to illustrate 
// bits.Mul32() Function 
package main 

import ( 
    "fmt"
    "math/bits"
) 

// Main function 
func main() { 

    // Using Mul32() function 
    hi, lo  := bits.Mul32(7, 2) 
    fmt.Println("64-bit product of x and y : ", hi, lo) 

}
```

**输出:**

```go
64-bit product of x and y :  0 14
```

**例 2:**

```go
// Golang program to illustrate 
// bits.Mul32() Function 
package main 

import ( 
    "fmt"
    "math/bits"
) 

// Main function 
func main() { 

    // Using Mul32() function 
    const a, b = 10, 20
    hi, lo  := bits.Mul32(a, b) 
    fmt.Println("Number 1:", a) 
    fmt.Println("Number 2:", b) 
    fmt.Println("Upper half:", hi) 
    fmt.Println("Lower half:", lo)  

}
```

**输出:**

```go
Number 1: 10
Number 2: 20
Upper half: 0
Lower half: 200

```