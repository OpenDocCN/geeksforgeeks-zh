# Golang

中的类型转换或类型转换

> Original: [https://www.geeksforgeeks.org/type-casting-or-type-conversion-in-golang/](https://www.geeksforgeeks.org/type-casting-or-type-conversion-in-golang/)

#### 先决条件：[Golang 数据类型](https://www.geeksforgeeks.org/data-types-in-go/)

当我们将一种数据类型的值赋给另一种数据类型时，就会发生类型转换。 静态类型语言，如[C](https://www.geeksforgeeks.org/c-programming-language/)/[C++](https://www.geeksforgeeks.org/c-plus-plus/)，[Java](https://www.geeksforgeeks.org/java/)，提供了对隐式类型转换的支持，但 Golang 不同，因为它**不支持*****自动类型转换或***隐式类型转换。 出现这种情况的原因是 Golang 的强类型系统不允许这样做。 对于类型转换，必须执行显式转换。
根据[Golang 规范](https://golang.org/ref/spec)，Golang 中没有类型转换单词或术语。 如果您尝试在 Golang 规范或文档中搜索 Type Cast，您将找不到这样的内容。 只有类型转换。 在其他编程语言中，类型转换也称为类型转换。
**什么是类型转换？**
那么，如果您需要利用数据类型层次结构的某些特性，那么我们必须将实体从一种数据类型转换为另一种数据类型。 将值*val*转换为类型*T*的一般语法为*T(Val)*。
**示例：**

```go
var geek1 int = 845

// explicit type conversion
var geek2 float64 = float64(geek1)

var geek3 int64 = int64(geek1)

var geek4 uint = uint(geek1)
```

## 电容 / 碳

```go
// Go program to find the
// average of numbers
package main

import "fmt"

func main() {

    // taking the required
    // data into variables
    var totalsum int = 846
    var number int = 19
    var avg float32

    // explicit type conversion
    avg = float32(totalsum) / float32(number)

    // Displaying the result
    fmt.Printf("Average = %f\n", avg)
}
```

发帖主题：Re：Колибри0.7.8.0

```go
Average = 44.526318
```

**注：**由于 Golang 具有强类型系统，不允许混合(如加、减、乘、除等)。 表达式中的数值类型，并且不允许在这两个混合类型之间执行赋值。
**示例：**

```go
var geek1 int64 = 875

// it will give compile time error as we
// are performing an assignment between
// mixed types i.e. int64 as int type
var geek2 int = geek1

var geek3 int = 100

// it gives compile time error
// as this is invalid operation
// because types are mix i.e.
// int64 and int
var addition = geek1 + geek3
```