# Golang 中的 time.Time.MarshalBinary()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-marshalbinary-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-marshalbinary-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 Go 语言中的**MarshalBinary()**函数用于实现*encoding.BinaryMarshaler*接口。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) MarshalBinary() ([]byte, error)

```

这里，“t”是指定的时间，在此方法中返回两个“byte”和“error”类型的值作为输出。

**返回值：**它返回一个表示接收器以二进制形式编码的字节片，还返回一个已发生的错误，但如果没有错误，则返回“nil”。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.MarshalBinary() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for MarshalBinary method
    t := time.Date(2001, 2, 1, 14, 30, 12, 05, time.UTC)

    // Calling MarshalBinary() method
    encoding, error := t.MarshalBinary()

    // Prints receiver's encoding
    fmt.Printf("Receiver's encoding: %v\n", encoding)

    // Prints error
    fmt.Printf("Error occurred: %v\n", error)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.MarshalBinary() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for MarshalBinary method
    t := time.Date(2021, 45, 56, 34, 76, 92, 66565, time.UTC)

    // Calling MarshalBinary() method
    encoding, error := t.MarshalBinary()

    // Prints receiver's encoding
    fmt.Printf("Receiver's encoding: %v\n", encoding)

    // Prints error
    fmt.Printf("Error occurred: %v\n", error)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面代码中声明的“t”具有超出通常范围的值，但它们在转换时被标准化。