# 格朗比特包

> 原文:[https://www.geeksforgeeks.org/bits-package-in-golang/](https://www.geeksforgeeks.org/bits-package-in-golang/)

Go 语言在 `bits` 包的帮助下，为预声明的无 unsigned 整数类型提供了对位计数和操作函数的内置支持。

| 功能 | 描述 |
| --- | --- |
| `Add` | 这个函数返回 `a`、`b` 和进位的和:和= a + b +进位。 |
| `Add32` | 这个函数返回 `a`、`b` 和进位的和:和= a + b +进位。 |
| `Add64` | 这个函数返回 `a`、`b` 和进位的和:和= a + b +进位。 |
| `Div` | 此函数返回 `(h, l)` 除以 `x` 的商和余数:`quo = (h, l)/x`，`rem = (hi, lo)%x`，被除数位的上半部分在参数 `h` 中，下半部分在参数 `l` 中。 |
| `Div32` | 此函数返回 `(h, l)` 除以 `x` 的商和余数:`quo = (h, l)/x`，`rem = (h, l)%x`，被除数位的上半部分在参数 `h` 中，下半部分在参数 `l` 中。 |
| `Div64` | 此函数返回 `(h, l)` 除以 `x` 的商和余数:`quo = (h, l)/x`，`rem = (h, l)%x`，被除数位的上半部分在参数 `h` 中，下半部分在参数 `l` 中。 |
| `LeadingZeros` | 此函数返回 `y` 中前导零位数。结果是 `x == 0` 的 `UintSize`。 |
| `LeadingZeros16` | 此函数返回 `y` 中前导零位数。对于 `y == 0`，结果为 16。 |
| `LeadingZeros32` | 此函数返回 `y` 中前导零位数。对于 `y == 0`，结果为 32。 |
| `LeadingZeros64` | 此函数返回 `y` 中前导零位数。对于 `y == 0`，结果为 64。 |
| `LeadingZeros8` | 此函数返回 `y` 中前导零位数。对于 `y == 0`，结果为 8。 |
| `Len` | 此函数返回表示 `y` 所需的最小位数。对于 `y == 0`，结果为 0。 |
| `Len16` | 此函数返回表示 `y` 所需的最小位数。对于 `y == 0`，结果为 0。 |
| `Len32` | 此函数返回表示 `y` 所需的最小位数。对于 `y == 0`，结果为 0。 |
| `Len64` | 此函数返回表示 `y` 所需的最小位数。对于 `y == 0`，结果为 0。 |
| `Len8` | 该函数返回表示 `y` 所需的最小位数，对于 `y == 0`，结果为 0。 |
| `Mul` | 该函数用于返回 `a` 和 `b` 的全宽乘积，即 `(hi, lo) = a * b`，乘积位的上半部分返回 `hi`，下半部分返回 `lo`。 |
| `Mul32` | 该函数用于返回 `a` 和 `b` 的 64 位乘积，即 `(hi, lo) = a * b`，乘积位的上半部分返回 `hi`，下半部分返回 `lo`。 |
| `Mul64` | 该函数用于返回 `a` 和 `b` 的 128 位乘积，即 `(hi, lo) = a * b`，乘积位的上半部分返回 `hi`，下半部分返回 `lo`。 |
| `OnesCount` | 该函数返回 `y` 中的一位数(“总数”)。 |
| `OnesCount16` | 该函数返回 `y` 中的一位数(“总数”)。 |
| `OnesCount32` | 该函数返回 `y` 中的一位数(“总数”)。 |
| `OnesCount64` | 该函数返回 `y` 中的一位数(“总数”)。 |
| `OnesCount8` | 该函数返回 `y` 中的一位数(“总数”)。 |
| `Rem` | 该函数返回 `(hi, lo)` 除以 `x` 的余数。 |
| `Rem32` | 该函数返回 `(hi, lo)` 除以 `x` 的余数。 |
| `Rem64` | 该函数返回 `(hi, lo)` 除以 `x` 的余数。 |
| `Reverse` | 该函数返回 `y` 的值，其位的顺序相反。 |
| `Reverse16` | 该函数返回 `y` 的值，其位的顺序相反。 |
| `Reverse32` | 该函数返回 `y` 的值，其位的顺序相反。 |
| `Reverse64` | 该函数返回 `y` 的值，其位的顺序相反。 |
| `Reverse8` | 该函数返回 `y` 的值，其位的顺序相反。 |
| `ReverseBytes` | 这个函数返回 `x` 的值，字节的顺序是相反的。 |
| `ReverseBytes16` | 这个函数返回 `x` 的值，字节的顺序是相反的。 |
| `ReverseBytes32` | 这个函数返回 `x` 的值，字节的顺序是相反的。 |
| `ReverseBytes64` | 这个函数返回 `x` 的值，字节的顺序是相反的。 |
| `RotateLeft` | 该函数返回向左旋转(`j mod UintSize`)位的 `y` 值。 |
| `RotateLeft16` | 该函数返回向左旋转(`j mod 16`)位的 `y` 值。 |
| `RotateLeft32` | 该函数返回向左旋转(`j mod 32`)位的 `y` 值。 |
| `RotateLeft64` | 该函数返回向左旋转(`j mod 64`)位的 `y` 值。 |
| `RotateLeft8` | 该函数返回向左旋转(`j mod 8`)位的 `y` 值。 |
| `Sub` | 该函数返回 `a`、`b` 和借位的差值:`diff = a–b–借位`。 |
| `Sub32` | 该函数返回 `a`、`b` 和借位的差值:`diff = a–b–借位`。 |
| `Sub64` | 该函数返回 `a`、`b` 和借位的差值:`diff = a–b–借位`。 |
| `TrailingZeros` | 此函数返回 `y` 中尾随的零位数。结果是 `y == 0` 的 `UintSize`。 |
| `TrailingZeros16` | 该函数返回 `y` 中尾随的零位数。对于 `y == 0`，结果是 16。 |
| `TrailingZeros32` | 该函数返回 `y` 中尾随的零位数。对于 `y == 0`，结果是 32。 |
| `TrailingZeros64` | 此函数返回 `y` 中尾随零位的数量。对于 `y == 0`，结果为 64。 |
| `TrailingZeros8` | 该函数返回 `y` 中尾随的零位数。对于 `y == 0`，结果是 8。 |

## 示例

### 例 1

```go
// Golang program to illustrate bits.Sub() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding diff and borrowOu
    // of the specified numbers
    // Using Sub() function
    nvalue_1, borrowOut := bits.Sub(4, 3, 0)
    fmt.Println("Diff:", nvalue_1)
    fmt.Println("BorrowOut :", borrowOut)
}
```

### 输出

```go
Diff: 1
BorrowOut : 0
```

### 例 2

```go
// Golang program to illustrate bits.TrailingZeros64() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using TrailingZeros64() function
    a := bits.TrailingZeros64(15)
    fmt.Printf("Total number of trailing"+
            " zero bits in %d: %d", 15, a)
}
```

### 输出

```go
Total number of trailing zero bits in 15: 0
```