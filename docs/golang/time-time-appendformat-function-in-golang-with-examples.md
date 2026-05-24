# Golang 中的 time.Time.AppendFormat()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-appendformat-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-appendformat-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 Go 语言中的**Time.AppendFormat()**函数类似于 format()方法，但此方法还将声明的文本表示附加到声明的“b”。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) AppendFormat(b []byte, layout string) []byte

```

这里，“t”是规定的时间，“b”是切片的字节，布局包含字符串类型。

**返回值：**它将文本表示形式附加到“b”，然后返回扩展的缓冲区。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.AppendFormat() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring Time
    Time := time.Date(2019, time.January, 
                1, 3, 0, 0, 0, time.UTC)

    // Defining byte of slice
    b := []byte("The time is: ")

    // Calling AppendFormat method with
    // its parameter
    b = Time.AppendFormat(b, "03:00PM")

    // Prints buffer
    fmt.Println(b)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，时间的文本表示被附加到“b”，然后它作为缓冲区返回。

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.AppendFormat() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring Time
    Time := time.Date(2019, time.January, 1, 
                      3, 0, 0, 0, time.UTC)

    // Defining byte of slice
    b := []byte("The time is: ")

    // Calling AppendFormat method with
    // its parameter
    b = Time.AppendFormat(b, time.Kitchen)

    // Prints string
    fmt.Println(string(b))
}
```

发帖主题：Re：Колибри0.7.8.0

这里，使用了预定义的布局，即*Time.Kitchen*，它在 Time.Format 中使用。 在上面的输出中，返回的是字符串而不是 Buffer，因为这里使用 string()方法将缓冲区转换为字符串。