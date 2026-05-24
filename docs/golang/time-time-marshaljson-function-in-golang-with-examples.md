# Golang 中的 time.Time.MarshalJSON()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-marshaljson-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-marshaljson-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**MarshalJSON()**函数用于实现*json.Marshaler*接口。 这里的时间是一个带引号的字符串，它是 RFC3339 格式的，如果有的话，还附带了次秒级的精度。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) MarshalJSON() ([]byte, error)

```

这里，“t”是指定的时间，在此方法中返回两个“byte”和“error”类型的值作为输出。

**返回值：**它返回一个表示 JSON 编码的字节片，它还返回一个已发生的错误，但如果没有错误，则返回“nil”。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.MarshalJSON() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for MarshalJSON method
    t := time.Date(2014, 11, 10, 14, 30, 12, 05, time.UTC)

    // Calling MarshalJSON() method
    encoding, error := t.MarshalJSON()

    // Prints JSON's encoding
    fmt.Printf("JSON's encoding: %v\n", encoding)

    // Prints error
    fmt.Printf("Error occurred: %v\n", error)
}
```

发帖主题：Re：Колибри0.7.0

> JSON 的编码：[34 50 48 49 52 45 49 45 49 48 84 49 52 58 58 49 50 46 48 48 48 53 90 34]
> 出现错误：<无>

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.MarshalJSON() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for MarshalJSON method
    t := time.Date(2022, 45, 67, 88, 67, 76, 903, time.UTC)

    // Calling MarshalJSON() method
    encoding, error := t.MarshalJSON()

    // Prints JSON's encoding
    fmt.Printf("JSON's encoding: %v\n", encoding)

    // Prints error
    fmt.Printf("Error occurred: %v\n", error)
}
```

发帖主题：Re：Колибри0.7.0

> JSON 的编码：[34 50 48 50 53 45 49 45 48 57 84 49 55 58 48 56 58 49 54 46 48 48 48 57 48 51 90 34]
> 出现错误：<无>

在这里，上面代码中声明的“t”具有超出通常范围的值，但它们在转换时被标准化。