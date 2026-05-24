# 位。Mul64()在 Golang 中的作用及实例

> 原文:[https://www . geesforgeks . org/bits-mul 64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-mul64-function-in-golang-with-examples/)

**位。Golang 中的 Mul64()函数**用来求 x 和 y 的 128 位乘积，这个函数的执行时间不依赖于输入。要访问这个函数，需要在程序中导入数学/位包。

**语法:**

```go
func Mul64(x, y uint64) (hi, lo uint64)
```

**参数:**该函数取 uint64 类型的两个参数，即 x，y。

**注:** (hi，lo) = x * y
这里，hi 是乘积位的上半部分，lo 是返回的下半部分。

**返回值:**该函数返回 x 和 y 的 **128 位乘积**

**例 1:**

```go
// Golang program to illustrate 
// bits.Mul64() Function 
package main 

import ( 
    "fmt"
    "math/bits"
) 

// Main function 
func main() { 

    // Using Mul64() function 
    hi, lo  := bits.Mul64(15, 25) 
    fmt.Println("128-bit product of x and y : ", hi, lo) 

}
```

**输出:**

```go
128-bit product of x and y :  0 375

```

**例 2:**

```go
// Golang program to illustrate 
// bits.Mul64() Function 
package main 

import ( 
    "fmt"
    "math/bits"
) 

// Main function 
func main() { 

    // Using Mul64() function 
    const a, b = 10, 30
    hi, lo  := bits.Mul64(a, b) 
    fmt.Println("Number 1:", a) 
    fmt.Println("Number 2:", b) 
    fmt.Println("Upper half:", hi) 
    fmt.Println("Lower half:", lo)  

}
```

**输出:**

```go
Number 1: 10
Number 2: 30
Upper half: 0
Lower half: 300

```