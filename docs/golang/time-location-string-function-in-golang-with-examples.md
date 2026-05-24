# Golang 中的 time.Location.String()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-location-string-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-location-string-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 Go 语言中的**Location.String()**函数用于查找为时区数据声明的解释性名称，该名称等同于传递给*LoadLocation*或*FixedZone*方法的 Name 参数。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些功能。

**语法：**

```go
func (l *Location) String() string

```

这里，“l”是要使用的位置的名称，而*location 是指向该位置的指针。 其中，“location”形成使用中的时间偏移量集合。

**返回值：**返回时区数据的说明性名称。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Location.String() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Calling LoadLocation 
    // method with its parameter
    locat, error := time.LoadLocation("Asia/Kolkata")

    // If error not 
    // equal to nil then
    // return panic error
    if error != nil {
        panic(error)
    }

    // Calling Location.String()
    // method and printing
    // location name
    fmt.Println(locat.String())
}
```

发帖主题：Re：Колибри0.7.0

```go
Asia/Kolkata

```

这里返回的是印度的 IANA 时区，因为没有错误。

**示例 2：**

```go
// Golang program to illustrate the usage of
// Location.String() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Calling FixedZone method
    // with its parameter
    location := time.FixedZone("UTC-7", -7*50*50)

    // Calling Location.String() 
    // method and printing
    // the stated location
    fmt.Println(location.String())
}
```

发帖主题：Re：Колибри0.7.0

```go
UTC-7

```