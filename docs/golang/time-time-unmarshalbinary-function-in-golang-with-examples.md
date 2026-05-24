# Golang 中的 time.Time.UnmarshalBinary()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-unmarshalbinary-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-unmarshalbinary-function-in-golang-with-examples/)

在围棋语言中，*Time*包提供了确定和查看时间的功能。 Go 语言中的**UnmarshalBinary()**函数用于实现*encoding.BinaryUnmarshaler*接口。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t *Time) UnmarshalBinary(data []byte) error

```

这里，“t”是指向指定时间的指针，“data”是对 MarshalBinary()方法生成的表单进行解码的字节片段。

**返回值：**它对 MarshalBinary()方法返回的表单进行解码，并返回错误，但如果没有错误，则返回“nil”。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.UnmarshalBinary() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for MarshalBinary method
    t := time.Date(2003, 4, 6, 12, 34, 33, 0, time.UTC)

    // Calling MarshalBinary() method
    encoding, _ := t.MarshalBinary()

    // Defining tm for UnmarshalBinary() method
    var tm time.Time

    // Calling GobDecode method with its parameters
    decode := tm.UnmarshalBinary(encoding)

    // Prints output
    fmt.Printf("Error: %v\n", decode)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.UnmarshalBinary() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t for MarshalBinary method
    t := time.Date(2020, 56, 76, 43, 99, 101, 3444, time.UTC)

    // Calling MarshalBinary() method
    encoding, _ := t.MarshalBinary()

    // Defining tm for UnmarshalBinary() method
    var tm time.Time

    // Calling GobDecode method with its parameters
    decode := tm.UnmarshalBinary(encoding)

    // Prints output
    fmt.Printf("Error: %v\n", decode)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面代码中声明的“t”具有超出通常范围的值，但它们在转换时被标准化。