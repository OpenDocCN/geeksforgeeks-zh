# 位。Golang 中 ReverseBytes64()函数示例

> 原文:[https://www . geesforgeks . org/bits-reversebytes64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-reversebytes64-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 **ReverseBytes64()函数**，该函数用于查找 a 值的逆序。要访问 ReverseBytes64()函数，您需要借助 import 关键字在程序中添加一个数学/位包。

**语法:**

```go
func ReverseBytes64(a uint64) uint64
```

**参数:**该函数取 uint64 类型的一个参数，即 a。

**返回值:**该函数返回一个的值，其位的顺序相反。

**例 1 :**

```go
// Golang program to illustrate
// bits.ReverseBytes64() Function

package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding the reverse order of a
    // Using ReverseBytes64() function
    a := bits.ReverseBytes64(7)
    fmt.Printf("Reverse order of %d: %b", 7, a)

}
```

**输出:**

```go
Reverse order of 7: 11100000000000000000000000000000000000000000000000000000000
```

**例 2:**

```go
// Golang program to illustrate
// bits.ReverseBytes64() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding the reverse order of a
    // Using ReverseBytes64() function
    a1 := bits.ReverseBytes64(3)
    fmt.Printf("ReverseBytes64(%064b) := %b\n", 3, a1)

    a2 := bits.ReverseBytes64(9)
    fmt.Printf("ReverseBytes64(%064b) := %b\n", 9, a2)

}
```

**输出:**

> 反向字节 64(000000000000 000000 000000 000000 0000001):= 110000000000000 000000 000000 000000 000000 000000 000000
> 反向字节 64(000000 000000 000000 000000 1001):= 1000000000000000000000 000000 000000 000000 000