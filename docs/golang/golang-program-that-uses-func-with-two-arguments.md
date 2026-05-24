# 使用带两个参数的 func 的 Golang 程序

> 原文:[https://www . geesforgeks . org/golang-使用双参数 func 的程序/](https://www.geeksforgeeks.org/golang-program-that-uses-func-with-two-arguments/)

[功能](https://www.geeksforgeeks.org/functions-in-go-language/)可以使用某些参数来接收值，并相应地执行所需的任务。具有两个参数的函数的语法是:

```go
func function_name( [parameter_1 parameter_2] ) [return_types]
{
   body of the function
}

```

**例 1:** 无任何返回类型

```go
// Golang program that uses func with
// two arguments without any return type

package main

import "fmt"

// Function accepting two arguments
// arguments defined as int type
func add(x int, y int) {
    var sum int = x + y
    fmt.Println(sum) // Prints the sum
}

// main function
func main() {

    add(10, 20) // Passing arguments
}
```

**输出:**

```go
30

```

**示例 2:** 带返回类型

```go
// Golang program that uses func with
// two arguments with any return type
package main

import "fmt"

// Function accepting two arguments
// arguments and return defined
// as int type
func add(x int, y int) int {
    var z int = x + y
    return z
}

// main function
func main() {

    // Passing arguments and receiving
    // the returned value in sum
    var sum = add(10, 20)
    // Prints the sum
    fmt.Println(sum)
}
```

**输出:**

```go
30

```