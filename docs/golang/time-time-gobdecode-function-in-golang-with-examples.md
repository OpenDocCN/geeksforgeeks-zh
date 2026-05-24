# Golang 中的 time.Time.GobDecode()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-gobdecode-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-gobdecode-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**GobDecode()**函数用于实现*gob.GobDecoder*接口。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t *Time) GobDecode(data []byte) error

```

这里，“t”是指向指定时间的指针，“data”是覆盖 GobEncode()方法返回的接收方编码的字节片。

**返回值：**它覆盖 GobEncode()方法返回的接收方编码，并返回错误，但如果没有错误，则返回“nil”。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.GobDecode() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for GobEncode method
    t := time.Date(2019, 4, 6, 12, 34, 33, 0, time.UTC)

    // Calling GobEncode() method
    encoding, error := t.GobEncode()

    // If error is not nil then panic error
    if error != nil {
        panic(error)
    }

    // Defining tm for GobDecode() method
    var tm time.Time

    // Calling GobDecode method with its parameters
    decode := tm.GobDecode(encoding)

    // Prints error
    fmt.Printf("Error: %v\n", decode)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.GobDecode() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for GobEncode method
    t := time.Date(2020, 44, 61, 37, 87, 72, 4566, time.UTC)

    // Calling GobEncode() method
    encoding, error := t.GobEncode()

    // If error is not nil then panic error
    if error != nil {
        panic(error)
    }

    // Defining tm for GobDecode() method
    var tm time.Time

    // Calling GobDecode method with its parameters
    decode := tm.GobDecode(encoding)

    // Prints error
    fmt.Printf("Error: %v\n", decode)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面代码中声明的“t”具有超出通常范围的值，但它们在转换时被标准化。