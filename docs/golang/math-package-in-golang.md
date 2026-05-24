# 格朗数学包

> 原文:[https://www.geeksforgeeks.org/math-package-in-golang/](https://www.geeksforgeeks.org/math-package-in-golang/)

Go 语言提供了对基本常数和数学函数的内置支持，以便在数学包的帮助下对数字进行运算。

| 功能 | 描述 |
| `Abs` | 此函数用于返回指定数字的绝对值。 |
| `Acos` | 此函数返回指定数值的反余弦值，单位为弧度。 |
| `Acosh` | 此函数返回指定数字的反双曲余弦值。 |
| `Asin` | 此函数返回指定数字的反正弦值，单位为弧度。 |
| `Asinh` | 此函数返回指定数字的反双曲正弦值。 |
| `Atan` | 此函数返回指定数值的反正切值，单位为弧度。 |
| `Atan2` | 此函数返回 a/b 的反正切，使用两者的符号来确定返回值的象限。 |
| `Atanh` | 此函数返回指定数字的反双曲正切值。 |
| `Cbrt` | 此函数返回指定数字的立方根。 |
| `Ceil` | 此函数返回大于或等于指定数字的最小整数值。 |
| `Copysign` | 这个函数返回一个值，大小为 a，符号为 b。 |
| `Cos` | 此函数返回指定数字弧度参数的余弦值。 |
| `Cosh` | 此函数返回指定数字的双曲余弦值。 |
| `Dim` | 该函数返回 a–b 或 0 的最大值。 |
| `Erf` | 该函数返回指定数字的误差函数。 |
| `Erfc` | 此函数返回指定数字的互补误差函数。 |
| `Erfcinv` | 该函数返回 Erfc(y)的倒数。 |
| `Erfinv` | 此函数返回指定数字的反向误差函数。 |
| `Exp` | 该函数返回 e**y，即指定数字的基数指数。 |
| `Exp2` | 这个函数返回 2**y，指定数字的 2 次幂。 |
| `Expm1` | 该函数返回 e * * y–1，即 y 减 1 的基本指数。 |
| `FMA` | 此函数返回一个* b + c，仅用一次舍入来计算。 |
| `Float32bits` | 这个函数返回 x 的 IEEE 754 二进制表示，x 的符号位和结果在相同的位位置。 |
| `Float32frombits` | 该函数返回与 IEEE 754 二进制表示 x 对应的浮点数，x 的符号位和结果位于相同的位位置。 |
| `Float64bits` | 这个函数返回 x 的 IEEE 754 二进制表示，x 的符号位和结果在相同的位位置，以及 float 64 bit(float 64 from bits(y))= = y。 |
| `Float64frombits` | 该函数返回与 IEEE 754 二进制表示 x 对应的浮点数，x 的符号位和结果位于相同的位位置。 |
| `Floor` | 此函数返回小于或等于指定数字的最大整数值。 |
| `Frexp` | 此函数用于将 t 分解为归一化分数和 2 的整数次幂，并返回满足 t == frac × 2**exp 的 frac 和 exp，frac 的绝对值在区间[，1]内。 |
| `Gamma` | 此函数返回指定数字的伽马函数。 |
| `Hypot` | 这个函数返回 Sqrt(a*a + b*b)，注意避免不必要的上溢和下溢。 |
| `Ilogb` | 此函数以整数形式返回指定数字的二进制指数。 |
| `Inf` | 如果符号> = 0，此函数返回正无穷大；如果符号< 0，则返回负无穷大。 |
| `IsInf` | 这个函数根据符号报告 t 是否为无穷大。 |
| `IsNaN` | 该函数报告 t 是否是 IEEE 754“非数字”值。 |
| `J0` | 该函数返回第一类零阶贝塞尔函数。 |
| `J1` | 这个函数返回第一类一阶贝塞尔函数。 |
| `Jn` | 该函数返回第一类 n 阶贝塞尔函数。 |
| `Ldexp` | 这个函数是 Frexp 的反函数。 |
| `Lgamma` | 该函数返回 Gamma(y)的自然对数和符号(-1 或+1)。 |
| `Log` | 此函数返回指定数字的自然对数。 |
| `Log10` | 此函数返回指定数字的十进制对数。 |
| `Log1p` | 此函数返回 1 的自然对数加上其指定数字的自变量。 |
| `Log2` | 此函数用于返回指定数字的二进制对数。 |
| `Logb` | 这个函数返回指定数字的二进制指数。 |
| `Max` | 此函数返回 a 或 b 中较大的一个。 |
| `Min` | 这个函数返回 a 和 b 中较小的一个。 |
| `Mod` | 此函数返回 a/b 的浮点余数 |
| `Modf` | 此函数返回整数和分数浮点数，它们的总和为 f。 |
| `NaN` | 该函数返回一个 IEEE 754“非数字”值。 |
| `Nextafter` | 该函数用于返回 a 之后的下一个可表示的浮点值。 |
| `Nextafter32` | 这个函数返回从 a 到 b 的下一个可表示的 float32 值。 |
| `Pow` | 这个函数返回一个**b，b 的基指数。 |
| `Pow10` | 这个函数返回 10**m，m 的 10 次幂。 |
| `Remainder` | 该函数返回 a/b 的 IEEE 754 浮点余数。 |
| `Round` | 该函数用于返回最近的整数，从零开始四舍五入。 |
| `RoundToEven` | 这个函数返回最近的整数，舍入到偶数。 |
| `Signbit` | 这个函数报告 x 是负的还是负的零。 |
| `Sin` | 这个函数返回弧度参数 y 的正弦值。 |
| `Sincos` | 这个函数返回 Sin(x)，Cos(x)。 |
| `Sinh` | 此函数返回指定数字的双曲正弦值。 |
| `Sqrt` | 此函数返回指定数字的平方根。 |
| `Tan` | 这个函数返回弧度参数 y 的正切值。 |
| `Tanh` | 此函数返回指定数字的双曲正切值。 |
| `Trunc` | 此函数返回指定数字的整数值。 |
| `Y0` | 这个函数返回第二类零阶贝塞尔函数。 |
| `Y1` | 这个函数返回第二类一阶贝塞尔函数。 |
| `Yn` | 这个函数返回第二类 n 阶贝塞尔函数。 |

**例 1:**

```go
// Golang program to illustrate how to 
// find the IEEE 754 binary representation 
package main 

import ( 
    "fmt"
    "math"
) 

// Main function 
func main() { 

    // Finding IEEE 754 binary 
    // representation of the 
    // given numbers 
    // Using Float64bits() function 
    res_1 := math.Float64bits(2) 
    res_2 := math.Float64bits(1) 
    res_3 := math.Float64bits(0) 
    res_4 := math.Float64bits(2.3) 

    // Displaying the result 
    fmt.Println("Result 1: ", res_1) 
    fmt.Println("Result 2: ", res_2) 
    fmt.Println("Result 3: ", res_3) 
    fmt.Println("Result 4: ", res_4) 

} 
```

**输出:**

```go
Result 1: 4611686018427387904
Result 2: 4607182418800017408
Result 3: 0
Result 4: 4612361558371493478

```

**例 2:**

```go
// Golang program to illustrate 
// the use of math.Yn() function 

package main 

import ( 
    "fmt"
    "math"
) 

// Main function 
func main() { 

    // Finding the order-n Bessel 
    // function of the second kind 
    // Using Yn() function 
    res_1 := math.Yn(-3, -2) 
    res_2 := math.Yn(6, 3) 
    res_3 := math.Yn(1, 1.1) 
    res_4 := math.Yn(1, math.NaN()) 
    res_5 := math.Yn(-1, 0) 

    // Displaying the result 
    fmt.Println("Result 1: ", res_1) 
    fmt.Println("Result 2: ", res_2) 
    fmt.Println("Result 3: ", res_3) 
    fmt.Println("Result 4: ", res_4) 
    fmt.Println("Result 5: ", res_5) 

} 
```

**输出:**

```go
Result 1:  NaN
Result 2:  -5.436470340703773
Result 3:  -0.698119560067667
Result 4:  NaN
Result 5:  +Inf

```