# Golang 中的空白标识符(下划线)是什么？

> Original: [https://www.geeksforgeeks.org/what-is-blank-identifierunderscore-in-golang/](https://www.geeksforgeeks.org/what-is-blank-identifierunderscore-in-golang/)

[Golang](https://www.geeksforgeeks.org/go-programming-language-introduction/)中的**_**(下划线)称为空白标识符。 [标识符](https://www.geeksforgeeks.org/identifiers-in-go-language/)是用于识别目的的程序组件的用户定义名称。 Golang 有一个特殊功能，可以使用空白标识符定义和使用未使用的变量。 未使用的变量是用户在整个程序中定义的那些[变量](https://www.geeksforgeeks.org/go-variables/)，但他/她从不使用这些变量。 这些变量使程序几乎不可读。 如您所知，Golang 是一种更简洁、更具可读性的编程语言，因此它不允许程序员定义未使用的变量。如果这样做，编译器将抛出错误。
当函数返回多个值，但我们只需要几个值并希望丢弃一些值时，才会真正使用空白标识符。 基本上，它告诉编译器不需要这个变量，并忽略它，没有任何错误。 它隐藏变量的值并使程序可读。 因此，只要您要为 Bank Identifier 赋值，它就会变得不可用。

**示例 1：**在下面的程序中，函数*mul_div*返回两个值，我们将这两个值都存储在*mul*和*div*标识符中。 但是在整个程序中，我们只使用了一个变量，即*mul*。 因此编译器将抛出错误`div declared and not used`

```go
// Golang program to show the compiler
// throws an error if a variable is
// declared but not used

package main

import "fmt"

// Main function
func main() {

    // calling the function
    // function returns two values which are
    // assigned to mul and div identifier
    mul, div := mul_div(105, 7)

    // only using the mul variable
    // compiler will give an error
    fmt.Println("105 x 7 = ", mul)
}

// function returning two 
// values of integer type
func mul_div(n1 int, n2 int) (int, int) {

    // returning the values
    return n1 * n2, n1 / n2
}
```

发帖主题：Re：Колибри0.7.0

```go
./prog.go:15:7: div declared and not used

```

**示例 2：**让我们使用空白标识符来更正上面的程序。 只需使用 _(下划线)代替 div 标识符。 它允许编译器忽略该特定变量的`declared and not used`错误。

```go
// Golang program to the use of Blank identifier

package main

import "fmt"

// Main function
func main() {

    // calling the function
    // function returns two values which are
    // assigned to mul and blank identifier
    mul, _ := mul_div(105, 7)

    // only using the mul variable
    fmt.Println("105 x 7 = ", mul)
}

// function returning two 
// values of integer type
func mul_div(n1 int, n2 int) (int, int) {

    // returning the values
    return n1 * n2, n1 / n2
}
```

发帖主题：Re：Колибри0.7.0

```go
105 x 7 =  735

```

**要点：**

*   您可以在同一程序中使用多个空白标识符。 所以可以说，Golang 程序可以有多个变量，使用相同的标识符名，即空标识符。
*   在很多情况下，即使知道这些值不会在程序中的任何地方使用，也会要求赋值只是为了完成语法。 类似于返回多个值的函数。 在这种情况下，大多数情况下使用空白标识符。
*   您可以将任何类型的任何值与空白标识符一起使用。