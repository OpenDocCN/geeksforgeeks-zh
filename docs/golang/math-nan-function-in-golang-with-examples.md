# Golang 中的 Math.NaN()函数，示例

> Original: [https://www.geeksforgeeks.org/math-nan-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-nan-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在数学包的帮助下对数字执行运算。 在**数学包**提供的**NaN()函数**的帮助下，您可以获得 IEEE754“not-a-number”值。 因此，您需要在程序中添加一个数学包，并借助 import 关键字访问 NaN()函数。

**语法：**

```go
func NaN() float64
```

**示例 1：**

```go
// Golang program to illustrate math.NaN() Function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Getting Not-a-number value
    // Using NaN() function
    res := math.NaN()

    // Displaying the result
    fmt.Println("Result: ", res)

}
```

发帖主题：Re：Колибри0.7.0

```go
Result:  NaN

```

**示例 2：**

```go
// Golang program to illustrate math.NaN() Function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Checking whether the given 
    // value is not-a-number or not
    // Using NaN() function
    nvalue := math.NaN()
    if nvalue == math.NaN() {
        fmt.Println("Given value is not-a-number")
    } else {
        fmt.Println("Given value is not a not-a-number")
    }

}
```

发帖主题：Re：Колибри0.7.0

```go
Given value is not a not-a-number
```