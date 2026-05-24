# Golang 中的 time.Time.MarshalText()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-marshaltext-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-marshaltext-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**MarshalText()**函数用于实现*encoding.TextMarshaler*接口。 这里的时间被格式化为 RFC3339 格式以及附加的亚秒精度(如果可用)。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) MarshalText() ([]byte, error)

```

这里，“t”是指定的时间，在此方法中返回两个“byte”和“error”类型的值作为输出。

**返回值：**它返回一个表示接收方编码为 UTF-8 编码文本的字节片，它还返回一个已发生的错误，但如果没有错误，则返回“nil”。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.MarshalText() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for MarshalText method
    t := time.Date(2001, 3, 6, 11, 45, 12, 03, time.UTC)

    // Calling MarshalText() method
    encoding, error := t.MarshalText()

    // Prints receiver's encoding
    fmt.Printf("Receiver's encoding: %v\n", encoding)

    // Prints error
    fmt.Printf("Error occurred: %v\n", error)
}
```

发帖主题：Re：Колибри0.7.0

> 接收方编码：[50 48 48 49 45 48 54 84 49 49 58 52 53 58 49 50 46 48 48 48 51 90]
> 出现错误：<nil>

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.MarshalText() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for MarshalText method
    t := time.Date(2022, 67, 45, 89, 78, 90, 4353, time.UTC)

    // Calling MarshalText() method
    encoding, error := t.MarshalText()

    // Prints receiver's encoding
    fmt.Printf("Receiver's encoding: %v\n", encoding)

    // Prints error
    fmt.Printf("Error occurred: %v\n", error)
}
```

发帖主题：Re：Колибри0.7.0

> 接收方编码：[50 48 50 55 45 48 56 45 49 55 84 49 56 58 49 57 58 51 48 46 48 48 48 52 51 53 51 90]
> 出现错误：<nil>

在这里，上面代码中声明的“t”具有超出通常范围的值，但它们在转换时被标准化。