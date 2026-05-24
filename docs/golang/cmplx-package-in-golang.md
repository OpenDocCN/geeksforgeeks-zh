# 格朗 cmplx 包装

> 原文:[https://www.geeksforgeeks.org/cmplx-package-in-golang/](https://www.geeksforgeeks.org/cmplx-package-in-golang/)

Go 语言借助 cmplx 包，为复数的基本常数和数学函数提供内置支持。

| 功能 | 描述 |
| **Abs** | 该函数返回指定复数的绝对值(也称为模)。 |
| acos | 该函数返回指定复数的反余弦值。 |
| **Acosh** | 此函数返回指定复数的反双曲余弦值。 |
| **Asin** | 该函数返回指定复数的反正弦值。 |
| 就用一个描述的网站描述了一个 1231 适合使用的样子 | 此函数返回指定复数的反双曲正弦值。 |
| **阿坦** | 该函数返回指定复数的反正切值。 |
| **阿坦** | 此函数返回指定复数的反双曲正切值。 |
| **Conj** | 该函数返回指定复数的复共轭。 |
| **Cos** | 此函数用于返回指定复数的余弦值。 |
| **Cosh** | 此函数返回指定复数的双曲余弦值。 |
| **Cot** | 这个函数返回指定复数的余切。 |
| **Exp** | 该函数返回 e**x，即指定复数的基数 e 指数。 |
| **Inf** | 这个函数返回一个复数无穷大，复数(+Inf，+Inf)。 |
| **IsInf** | 该函数报告实数(x)或 imag(x)是否为无穷大。 |
| **IsNan** | 该函数报告实数(x)或 imag(x)是否为 NaN，两者都不是无穷大。 |
| **日志** | 此函数返回指定复数的自然对数。 |
| **Log10** | 此函数返回指定复数的十进制对数。 |
| **NaN** | 这个函数返回一个复杂的“非数字”值。 |
| **阶段** | 该函数返回指定复数的相位(也称为自变量)。 |
| **极地** | 该函数返回 x 的绝对值 r 和相位θ，使得 x = r * e**θi。 |
| **动力** | 这个函数返回 x**y，y 的基指数 |
| **直肠** | 这个函数返回带有极坐标 r，θ的复数 x。 |
| **罪恶** | 该函数返回指定复数的正弦值。 |
| **辛赫** | 此函数返回指定复数的双曲正弦值。 |
| **Sqrt** | 此函数返回指定复数的平方根。 |
| **谭** | 该函数返回指定复数的正切值。 |
| **Tanh** | 此函数返回指定复数的双曲正切值。 |

**例 1:**

```go
// Golang program to illustrate how to find 
// the sine value of the given complex number 

package main 

import ( 
    "fmt"
    "math/cmplx"
) 

// Main function 
func main() { 

    // Finding sine of the  
    // specified complex number 
    // Using Sin() function 
    res_1 := cmplx.Sin(2 + 5i) 
    res_2 := cmplx.Sin(-1 + 8i) 
    res_3 := cmplx.Sin(-1 - 7i) 

    // Displaying the result 
    fmt.Println("Result 1:", res_1) 
    fmt.Println("Result 2:", res_2) 
    fmt.Println("Result 3:", res_3) 
} 
```

**输出:**

```go
Result 1: (67.47891523845587-30.879431343588244i)
Result 2: (-1254.1949676545178+805.3091464217314i)
Result 3: (-461.3928755590023-296.25646574921427i)

```

**例 2:**

```go
// Golang program to illustrate 
// how to find absolute value 
package main 

import ( 
    "fmt"
    "math/cmplx"
) 

// Main function 
func main() { 

    // Finding absolute value of 
    // the specified complex number 
    // Using Abs() function 
    res_1 := cmplx.Abs(3 + 5i) 
    res_2 := cmplx.Abs(-4 + 8i) 
    res_3 := cmplx.Abs(-8 - 7i) 

    // Displaying the result 
    fmt.Println("Random Number 1:", res_1) 
    fmt.Println("Random Number 2: ", res_2) 
    fmt.Println("Random Number 3: ", res_3) 
} 
```

**输出:**

```go
Random Number 1: 5.8309518948453
Random Number 2:  8.94427190999916
Random Number 3:  10.63014581273465

```