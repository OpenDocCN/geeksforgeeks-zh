# 如何在 Golang 中使用新函数创建自定义错误？

> 原文:[https://www . geesforgeks . org/如何使用 golang 中的新函数创建自定义错误/](https://www.geeksforgeeks.org/how-to-create-custom-errors-using-new-function-in-golang/)

自定义错误是那些可以由用户定义的错误。例如，如果一个人编写了一个用于将两个数字相除的函数，该函数将在多个地方使用，那么用户可能会创建一个自定义错误，只要遇到被零除的情况，就可以设置该错误，因为从长远来看，这可能是致命的。

在 Golang 中创建自定义错误最简单的方法是使用 *New()函数*，该函数存在于 Golang 的错误模块中。在真正开始创建我们自己的错误之前，让我们看看它是如何在**错误包**中实现的。

```go
package errors

// New returns an errorString
// that contains the input 
// text as its value.
func New(text string) error {
    return &errorString{text}
}

// errorString is a trivial
// implementation of error.
type errorString struct {
    s string
}

func (e *errorString) Error() string {
    return e.s
}
```

因此，基本上 New()函数所做的就是用程序员可以编写的自定义消息创建一个错误。例如，假设我们希望每当给定一个负值作为输出正方形面积的程序的输入时，显示一个错误，给定它的边。

```go
package main

// the errors package 
// contains the New function
import (
    "errors" 
    "fmt"
)

func main() {
    side := -2.0
    if side < 0.0 {

            // control enters here if error condition is met
        fmt.Println(errors.New("Negative value entered!")) 
        return
    }
    fmt.Printf("Area= %f", side*side)

}
```

**输出:**

```go
Negative value entered!

```

这是因为我们输入了边长为-2，这是不可能的，因此抛出了错误。现在让我们尝试一个类似的程序，但这次让我们把错误生成放在一个单独的函数中。

```go
package main

import (
    "errors"
    "fmt"
)

func findAreaSquare(side float64) (error, float64) {
    if side < 0.0 {

        // function that returns the error
        // as well as the computed area
        return errors.New("Negative value entered!"), 0
    }
    return nil, side * side
}
func main() {
    side := -2.0
    err, area := findAreaSquare(side)
    if err != nil {
        fmt.Printf("%s", err)
        return
    }
    fmt.Printf("Area= %f", area)

}
```

**输出:**

```go
Negative value entered!

```