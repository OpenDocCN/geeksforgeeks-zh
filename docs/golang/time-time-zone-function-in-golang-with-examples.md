# Golang 中的 time.Time.Zone()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-zone-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-zone-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**Time.Zone()**函数用于确定在时间“t”工作的时区。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) Zone() (name string, offset int)

```

这里，“t”是指定的时间，返回的“name”是 String 类型，返回的“Offset”是 int 类型。

**返回值：**它返回缩短的区域名称及其在 UTC 以东的偏移量(以秒为单位)。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.Zone() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining location using FixedZone method
    loc := time.FixedZone("UTC-7", 1*13*16)

    // Declaring t for Zone method
    t := time.Date(2014, 6, 5, 11, 56, 45, 05, loc)

    // Calling Zone() method
    zone_name, offset := t.Zone()

    // Prints zone name
    fmt.Printf("The zone name is: %s\n", zone_name)

    // Prints offset
    fmt.Printf("The offset returned is: %d\n", offset)
}
```

发帖主题：Re：Колибри0.7.8.0

这里，我们使用 FixedZone()方法来指定区域名称和偏移量。

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.Zone() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining location using FixedZone method
    loc := time.FixedZone("UTC-6", -4*23*16)

    // Declaring t for Zone method
    t := time.Date(2014, 32, 35, 64, 76, 98, 3432, loc)

    // Calling Zone() method
    zone_name, offset := t.Zone()

    // Prints zone name
    fmt.Printf("The zone name is: %s\n", zone_name)

    // Prints offset
    fmt.Printf("The offset returned is: %d\n", offset)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面提到的“t”的值超出了通常的范围，但它们在转换时被标准化了。