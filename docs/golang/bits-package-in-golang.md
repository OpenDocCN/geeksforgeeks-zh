# 格朗比特包

> 原文:[https://www.geeksforgeeks.org/bits-package-in-golang/](https://www.geeksforgeeks.org/bits-package-in-golang/)

Go 语言在 bits 包的帮助下，为预声明的无符号整数类型提供了对位计数和操作函数的内置支持。

| 功能 | 描述 |
| **[增加](https://www.geeksforgeeks.org/bits-add-function-in-golang-with-examples/)** | 这个函数返回 a、b 和进位的和:和= a + b +进位。 |
| **[Add32](https://www.geeksforgeeks.org/bits-add32-function-in-golang-with-examples/)** | 这个函数返回 a、b 和进位的和:和= a + b +进位。 |
| **[Add64](https://www.geeksforgeeks.org/bits-add64-function-in-golang-with-examples/)** | 这个函数返回 a、b 和进位的和:和= a + b +进位。 |
| **[Div](https://www.geeksforgeeks.org/bits-div-function-in-golang-with-examples/)** | 此函数返回(h，l)除以 x 的商和余数:quo = (h，l)/x，rem = (hi，lo)%x，被除数位的上半部分在参数 h 中，下半部分在参数 l 中。 |
| **[【div 32】](https://www.geeksforgeeks.org/bits-div32-function-in-golang-with-examples/)** | 此函数返回(h，l)除以 x 的商和余数:quo = (h，l)/x，rem = (h，l)%x，被除数位的上半部分在参数 h 中，下半部分在参数 l 中。 |
| **[【div 64】](https://www.geeksforgeeks.org/bits-div64-function-in-golang-with-examples/)** | 此函数返回(h，l)除以 x 的商和余数:quo = (h，l)/x，rem = (h，l)%x，被除数位的上半部分在参数 h 中，下半部分在参数 l 中。 |
| **[前导零](https://www.geeksforgeeks.org/bits-leadingzeros-function-in-golang-with-examples/)** | 此函数返回 y 中前导零位数。结果是 x == 0 的 UintSize。 |
| **[领零 16](https://www.geeksforgeeks.org/bits-leadingzeros16-function-in-golang-with-examples/)** | 此函数返回 y 中前导零位数。对于 y == 0，结果为 16。 |
| **[领零 32](https://www.geeksforgeeks.org/bits-leadingzeros32-function-in-golang-with-examples/)** | 此函数返回 y 中前导零位数。对于 y == 0，结果为 32。 |
| **[领零 64](https://www.geeksforgeeks.org/bits-leadingzeros64-function-in-golang-with-examples/)** | 此函数返回 y 中前导零位数。对于 y == 0，结果为 64。 |
| **[前导零 8](https://www.geeksforgeeks.org/bits-leadingzeros8-function-in-golang-with-examples/)** | 此函数返回 y 中前导零位数。对于 y == 0，结果为 8。 |
| **[伦](https://www.geeksforgeeks.org/bits-len-function-in-golang-with-examples/)** | 此函数返回表示 y 所需的最小位数。对于 y == 0，结果为 0。 |
| **T1】Len16T3】** | 此函数返回表示 y 所需的最小位数。对于 y == 0，结果为 0。 |
| **[历 32](https://www.geeksforgeeks.org/bits-len32-function-in-golang-with-examples/)** | 此函数返回表示 y 所需的最小位数。对于 y == 0，结果为 0。 |
| **T1】Len64T3】** | 此函数返回表示 y 所需的最小位数。对于 y == 0，结果为 0。 |
| **[【伦 8】](https://www.geeksforgeeks.org/bits-len8-function-in-golang-with-examples/)** | 该函数返回表示 y 所需的最小位数，对于 y == 0，结果为 0。 |
| **[穆尔](https://www.geeksforgeeks.org/bits-mul-function-in-golang-with-examples/)** | 该函数用于返回 a 和 b 的全宽乘积，即(hi，lo) = a * b，乘积位的上半部分返回 hi，下半部分返回 lo。 |
| **[Mul32](https://www.geeksforgeeks.org/bits-mul32-function-in-golang-with-examples/)** | 该函数用于返回 a 和 b 的 64 位乘积，即(hi，lo) = a * b，乘积位的上半部分返回 hi，下半部分返回 lo。 |
| **[Mul64](https://www.geeksforgeeks.org/bits-mul64-function-in-golang-with-examples/)** | 该函数用于返回 a 和 b 的 128 位乘积，即(hi，lo) = a * b，乘积位的上半部分返回 hi，下半部分返回 lo。 |
| **[【onescont】](https://www.geeksforgeeks.org/bits-onescount-function-in-golang-with-examples/)** | 该函数返回 y 中的一位数(“总数”)。 |
| **[onescont 16](https://www.geeksforgeeks.org/bits-onescount16-function-in-golang-with-examples/)** | 该函数返回 y 中的一位数(“总数”)。 |
| **[onescont 32](https://www.geeksforgeeks.org/bits-onescount32-function-in-golang-with-examples/)** | 该函数返回 y 中的一位数(“总数”)。 |
| **[OnesCount64](https://www.geeksforgeeks.org/bits-onescount64-function-in-golang-with-examples/)** | 该函数返回 y 中的一位数(“总数”)。 |
| **[【onescount 8】](https://www.geeksforgeeks.org/bits-onescount8-function-in-golang-with-examples/)** | 该函数返回 y 中的一位数(“总数”)。 |
| **[【rem】](https://www.geeksforgeeks.org/bits-rem-function-in-golang-with-examples/)** | 该函数返回(hi，lo)除以 x 的余数。 |
| **[【rem 32】](https://www.geeksforgeeks.org/bits-rem32-function-in-golang-with-examples/)** | 该函数返回(hi，lo)除以 x 的余数。 |
| **[【rem 64】](https://www.geeksforgeeks.org/bits-rem64-function-in-golang-with-examples/)** | 该函数返回(hi，lo)除以 x 的余数。 |
| **[倒车](https://www.geeksforgeeks.org/bits-reverse-function-in-golang-with-examples/)** | 该函数返回 y 的值，其位的顺序相反。 |
| **[反转 16](https://www.geeksforgeeks.org/bits-reverse16-function-in-golang-with-examples/)** | 该函数返回 y 的值，其位的顺序相反。 |
| **[反转 32](https://www.geeksforgeeks.org/bits-reverse32-function-in-golang-with-examples/)** | 该函数返回 y 的值，其位的顺序相反。 |
| **[反转 64](https://www.geeksforgeeks.org/bits-reverse64-function-in-golang-with-examples/)** | 该函数返回 y 的值，其位的顺序相反。 |
| **[反转 8](https://www.geeksforgeeks.org/bits-reverse8-function-in-golang-with-examples/)** | 该函数返回 y 的值，其位的顺序相反。 |
| **[反向字节](https://www.geeksforgeeks.org/bits-reversebytes-function-in-golang-with-examples/)** | 这个函数返回 x 的值，字节的顺序是相反的。 |
| **[反向字节 16](https://www.geeksforgeeks.org/bits-reversebytes16-function-in-golang-with-examples/)** | 这个函数返回 x 的值，字节的顺序是相反的。 |
| **[反向字节 32](https://www.geeksforgeeks.org/bits-reversebytes32-function-in-golang-with-examples/)** | 这个函数返回 x 的值，字节的顺序是相反的。 |
| **[反向字节 64](https://www.geeksforgeeks.org/bits-reversebytes64-function-in-golang-with-examples/)** | 这个函数返回 x 的值，字节的顺序是相反的。 |
| **[旋转动作](https://www.geeksforgeeks.org/bits-rotateleft-function-in-golang-with-examples/)** | 该函数返回向左旋转(j mod UintSize)位的 y 值。 |
| **[旋转飞秒 16](https://www.geeksforgeeks.org/bits-rotateleft16-function-in-golang-with-examples/)** | 该函数返回向左旋转(j mod 16)位的 y 值。 |
| **[旋转 ft32](https://www.geeksforgeeks.org/bits-rotateleft32-function-in-golang-with-examples/)** | 该函数返回向左旋转(j mod 32)位的 y 值。 |
| **旋转翼 64 旋转翼 3** | 该函数返回向左旋转(j mod 64)位的 y 值。 |
| **[旋转飞秒 8](https://www.geeksforgeeks.org/bits-rotateleft8-function-in-golang-with-examples/)** | 该函数返回向左旋转(j mod 8)位的 y 值。 |
| **[子](https://www.geeksforgeeks.org/bits-sub-function-in-golang-with-examples/)** | 该函数返回 a、b 和借位的差值:diff = a–b–借位。 |
| **[Sub32](https://www.geeksforgeeks.org/bits-sub32-function-in-golang-with-examples/)** | 该函数返回 a、b 和借位的差值:diff = a–b–借位。 |
| **[Sub64](https://www.geeksforgeeks.org/bits-sub64-function-in-golang-with-examples/)** | 该函数返回 a、b 和借位的差值:diff = a–b–借位。 |
| **T1 列车** | 此函数返回 y 中尾随的零位数。结果是 y == 0 的 UintSize。 |
| **[火车 16](https://www.geeksforgeeks.org/bits-trailingzeros16-function-in-golang-with-examples/)** | 该函数返回 y 中尾随的零位数。对于 y == 0，结果是 16。 |
| **[列车 32](https://www.geeksforgeeks.org/bits-trailingzeros32-function-in-golang-with-examples/)** | 该函数返回 y 中尾随的零位数。对于 y == 0，结果是 32。 |
| **T1 火车 64** | 此函数返回 y 中尾随零位的数量。对于 y == 0，结果为 64。 |
| **[火车日 8](https://www.geeksforgeeks.org/bits-trailingzeros8-function-in-golang-with-examples/)** | 该函数返回 y 中尾随的零位数。对于 y == 0，结果是 8。 |

**例 1:**

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

**输出:**

```go
Diff: 1
BorrowOut : 0
```

**例 2:**

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

**输出:**

```go
Total number of trailing zero bits in 15: 0
```