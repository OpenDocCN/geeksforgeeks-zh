# Golang 中的 math.Float32bits()函数，示例为

> Original: [https://www.geeksforgeeks.org/math-float32bits-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-float32bits-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在数学包的帮助下对数字执行运算。 此软件包提供**Float32bits()函数**，该函数返回 a 的 IEEE 754 二进制表示，符号位为 a，结果位于相同的位位置。 因此，您需要在程序中添加一个数学包，并借助 IMPORT 关键字访问 Float32bit()函数

**语法：**

```go
func Float32bits(a float32) uint32
```

**示例 1：**

```go
// Golang program to illustrate how to
// find IEEE 754 binary representation
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
    // Using Float32bits() function
    res_1 := math.Float32bits(-2)
    res_2 := math.Float32bits(1)
    res_3 := math.Float32bits(0)
    res_4 := math.Float32bits(2.3)

    // Displaying the result
    fmt.Println("Result 1: ", res_1)
    fmt.Println("Result 2: ", res_2)
    fmt.Println("Result 3: ", res_3)
    fmt.Println("Result 4: ", res_4)

}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1:  3221225472
Result 2:  1065353216
Result 3:  0
Result 4:  1075000115

```

**示例 2：**

```go
// Golang program to illustrate how to
// find IEEE 754 binary representation
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
    // Using Float32bits() function
    nvalue_1 := math.Float32bits(3)
    nvalue_2 := math.Float32bits(5)

    // Sum of the given values
    res := nvalue_1 + nvalue_2
    fmt.Printf("%d + %d = %d",
      nvalue_1, nvalue_2, res)

}
```

发帖主题：Re：Колибри0.7.0

```go
1077936128 + 1084227584 = 2162163712
```