# Golang 中的 time.ParseError.Error()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-parseerror-error-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-parseerror-error-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**ParseError.Error()**函数用于输出*ParseError*的字符串描述。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些功能。

**语法：**

```go
func (e *ParseError) Error() string

```

这里，“e”是指向 ParseError 的指针，ParseError 用于解释解析时间字符串的问题。

**返回值：**它返回*ParseError*的字符串表示形式。

**示例 1：**

```go
// Golang program to illustrate the usage of
// time.ParseError() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring a struct
    // type ParseError
    // with its values
    error := time.ParseError{
        Value:   "1122020",
        Message: " There is an error!",
    }

    // Calling Error method 
    // and printing string
    // representation of ParseError
    fmt.Println(error.Error())
}
```

发帖主题：Re：Колибри0.7.8.0

这里，返回结构类型*ParseError*中值和消息的字符串表示。

**示例 2：**

```go
// Golang program to illustrate the usage of
// time.ParseError() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring a struct 
    // type ParseError
    // with its values
    error := time.ParseError{
        Layout:    "2001 12 01",
        Value:     "11:34:09",
        ValueElem: "11",
        Message:   " An error occurred!",
    }

    // Calling Error method 
    // and printing string
    // representation of ParseError
    fmt.Println(error.Error())
}
```

发帖主题：Re：Колибри0.7.8.0

它与上面的示例相同，但是这里在 ParseError 结构类型中使用了更多的值。