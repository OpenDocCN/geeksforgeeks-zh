# Golang 中的 time.After()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-after-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-after-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**After()**函数用于等待经过的持续时间，然后在返回的[通道](https://www.geeksforgeeks.org/channel-in-golang/)上提供实际时间。 此外，该函数在**时间包**下定义。 在这里，您需要导入“time”包才能使用这些功能。

**语法：**

```go
func After(d Duration) <-chan Time

```

这里，*d*是超时之前的持续时间，*chan*是发送当前时间的通道。

**返回值：**先等待指定时间，然后显示超时。

**示例 1：**

```go
// Golang program to illustrate the usage of
// After() function in Golang

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Creating a channel
// Using var keyword
var ch chan int

// Main function
func main() {

    // For loop
    for i := 1; i < 6; i++ {

        // Prints these util loop stops
        fmt.Println("****Welcome to GeeksforGeeks***")
        fmt.Println("A CS-Portal!")
    }

    // Select statement
    select {

    // Using case statement to receive
    // or send operation on channel and
    // calling After() method with its
    // parameter
    case <-time.After(3 * time.Second):

        // Printed when timed out
        fmt.Println("Time Out!")
    }
}
```

发帖主题：Re：Колибри0.7.8.0

在上面的示例中，我们在 SELECT 语句下使用了“case”语句，以便在通道上发送操作。 此外，此处将在执行 for 循环的 3 秒后显示超时。

**示例 2：**

```go
// Golang program to illustrate the usage of
// After() function in Golang

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Main function
func main() {

    // Creating a channel
    // Using make keyword
    channel := make(chan string, 2)

    // Select statement
    select {

    // Using case statement to receive
    // or send operation on channel
    case output := <-channel:
        fmt.Println(output)

    // Calling After() method with its
    // parameter
    case <-time.After(5 * time.Second):

        // Printed after 5 seconds
        fmt.Println("Its timeout..")
    }
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，我们使用了“make”关键字来创建一个频道，然后就像上面的例子一样，在 SELECT 语句下也使用了 case 语句，但在这里它被使用了两次。 第一个用于返回输出，第二个用于在通道上的()方法之后调用*。 在此之后，将在规定的时间内显示超时。*