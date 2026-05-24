# 如何在 Golang 中将 Int 数据类型转换为 Float？

> 原文:[https://www . geesforgeks . org/如何将 int-data-type 转换为 float-in-golang/](https://www.geeksforgeeks.org/how-to-convert-int-data-type-to-float-in-golang/)

在 Golang 中，[数据类型](https://www.geeksforgeeks.org/data-types-in-go/)绑定到变量而不是值，这意味着，如果您将变量声明为 **int** ，那么您只能在其中存储整数类型值，除非您将数据类型转换为所需的数据类型，否则您不能在其中分配字符或字符串。

要将整数数据类型转换为浮点型，可以用 float64()或 float32 包装该整数。

**例:**

```go
// Golang program to convert Int data type to Float
package main

import (
    "fmt"
    "reflect"
)

func main() {

    // var declared x as int
    var x int64 = 5

    // y is a float64 type variable
    var y float64 = float64(x)

    // printing the values of x and y
    fmt.Printf("x = %d \n", x)
    fmt.Printf("y = %f \n", y)

    // to print a float upto a
    // specific number of decimal point
    fmt.Printf("\ny upto 3 decimal = %.3f", y)

    // getting the converted type
    fmt.Println("\n", reflect.TypeOf(y))

}
```

**输出**

```go
x = 5 
y = 5.000000 

y upto 3 decimal = 5.000
 float64

```

**解释:**首先我们声明一个 int64 类型的变量 **x** ，值为 **5** 。然后我们用 **float64()** 包裹 **x** ，将整数 5 转换为 **5.00** 的 float 值。 **%.3f** 将浮点值格式化至小数点后 3 位。