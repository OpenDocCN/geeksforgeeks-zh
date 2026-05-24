# Golang 中的 time.Time.UnmarshalJSON()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-unmarshaljson-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-unmarshaljson-function-in-golang-with-examples/)

在围棋语言中，*Time*包提供了确定和查看时间的功能。 GO 语言中的**UnmarshalJSON()**函数用于实现*json.Unmarshaler*接口。 这里的时间是一个带引号的字符串，格式为 RFC 3339。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t *Time) UnmarshalJSON(data []byte) error

```

这里，“t”是指向指定时间的指针，“data”是表示由 MarshalJSON()方法生成的 JSON 编码的字节片。

**返回值：**它对 MarshalJSON()方法返回的编码进行解码，并返回错误，但如果没有错误，则返回“nil”。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.UnmarshalJSON() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for MarshalJSON method
    t := time.Date(2013, 7, 6, 12, 34, 33, 01, time.UTC)

    // Calling MarshalJSON() method
    encoding, _ := t.MarshalJSON()

    // Defining tm for UnmarshalJSON() method
    var tm time.Time

    // Calling UnmarshalJSON method with its parameters
    decode := tm.UnmarshalJSON(encoding)

    // Prints output
    fmt.Printf("Error: %v\n", decode)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.UnmarshalJSON() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for MarshalJSON method
    t := time.Date(2034, 45, 33, 43, 90, 70, 6447, time.UTC)

    // Calling MarshalJSON() method
    encoding, _ := t.MarshalJSON()

    // Defining tm for UnmarshalJSON() method
    var tm time.Time

    // Calling UnmarshalJSON method with its parameters
    decode := tm.UnmarshalJSON(encoding)

    // Prints output
    fmt.Printf("Error: %v\n", decode)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面代码中声明的“t”具有超出通常范围的值，但它们在转换时被标准化。