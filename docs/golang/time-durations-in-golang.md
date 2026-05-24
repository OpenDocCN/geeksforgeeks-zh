# 以 Golang 为单位的持续时间

> Original: [https://www.geeksforgeeks.org/time-durations-in-golang/](https://www.geeksforgeeks.org/time-durations-in-golang/)

与时间和日期相关的操作是软件开发(示例日志保存)的关键部分。 围棋标准库提供了一个时间包，它有很多处理日期和时间的函数和方法。 操作系统测量两种类型的时间：“挂钟”时间和“单调”时间。 墙上的时钟时间是用来报时的，而单调的时钟时间是用来测量时间的。 Go Time Package 提供测量和操作两个时钟的功能。 Golang 有*time.Time*数据类型来处理挂钟时间，*time.Duration*来处理单调时间。(
第一个基本方法是 time.Now()，它返回当前日期和时间，精度达到纳秒。 返回的值具有数据类型 time.Time，它是一个结构。 根据 Golang 的官方文件，“时间以纳秒的精度代表时间的一瞬间。”

## 行走 / 离开 / 变成 / 走

```go
package main

import (
    "fmt"
    "time"
)

func main() {

    // Returns current time.
    t := time.Now()
    fmt.Println(t)
}
```

发帖主题：Re：Колибри0.7.0

```go
2020-04-29 00:37:36.849599502 +0530 IST m=+0.000166550 
```

在 GO 中，任何已声明但未初始化的变量在缺省情况下都设置为其零值。 TIME 类型的零值是 1，00：00：00.000000000 UTC，这在实际情况下是不可能的。 **IsZero 方法**也可用于检查时间变量是否初始化。

## 行走 / 离开 / 变成 / 走

```go
package main

import (
    "fmt"
    "time"
)

func main() {
    var t time.Time
    fmt.Println(t)
    fmt.Println(t.IsZero())
}
```