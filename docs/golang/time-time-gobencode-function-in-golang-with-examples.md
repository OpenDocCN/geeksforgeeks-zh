# Golang 中的 time.Time.GobEncode()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-gobencode-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-gobencode-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**GobEncode()**函数用于实现*gob.GobEncode*接口。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) GobEncode() ([]byte, error)

```

这里，“t”是指定的时间，在此方法中返回两个“byte”和“error”类型的值作为输出。

**返回值：**它返回表示接收器编码的字节片，以便可以将其传输到*GobDecoder*，并且还返回发生错误，但如果没有错误，则返回“nil”。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.GobEncode() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for GobEncode method
    t := time.Date(2018, 2, 1, 14, 30, 0, 0, time.UTC)

    // Calling GobEncode() method
    encoding, error := t.GobEncode()

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
// Time.GobEncode() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for GobEncode method
    t := time.Date(2019, 37, 43, 76, 90, 88, 5453, time.UTC)

    // Calling GobEncode() method
    encoding, error := t.GobEncode()

    // Prints receiver's encoding
    fmt.Printf("Receiver's encoding: %v\n", encoding)

    // Prints error
    fmt.Printf("Error occurred: %v\n", error)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面代码中声明的“t”具有超出通常范围的值，但它们在转换时被标准化。