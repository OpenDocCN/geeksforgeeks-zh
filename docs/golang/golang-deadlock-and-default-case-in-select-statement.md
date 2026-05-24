# Golang | Select 语句中的死锁和默认情况

> 原文:[https://www . geesforgeks . org/golang-死锁和默认情况下选择语句/](https://www.geeksforgeeks.org/golang-deadlock-and-default-case-in-select-statement/)

在 Go 语言中， [select 语句](https://www.geeksforgeeks.org/select-statement-in-go-language/)就像一个 [switch 语句](https://www.geeksforgeeks.org/switch-statement-in-go/)，但是在 select 语句中，case 语句指的是通信，即在信道上发送或接收的操作。

**语法:**

```go
select{

case SendOrReceive1: // Statement
case SendOrReceive2: // Statement
case SendOrReceive3: // Statement
.......
default: // Statement

```

在本文中，我们将学习如何使用默认案例来避免死锁。但是首先，我们了解什么是死锁？

**死锁:**当您试图从通道读取或写入数据，但通道没有值时。因此，它会阻止 goro tine 的当前执行，并将控制权交给其他[goro tine](https://www.geeksforgeeks.org/goroutines-concurrency-in-golang/)，但是如果没有其他 goro tine 可用，或者其他 goro tine 由于这种情况正在休眠，程序将会崩溃。这种现象被称为死锁。如下例所示:

**示例:**

```go
// Go program to illustrate
// how deadlock arises
package main

// Main function
func main() {

    // Creating a channel
    // Here  deadlock arises because
    // no goroutine is writing
    // to this channel so, the select 
    // statement has been blocked forever
    c := make(chan int)
    select {
    case <-c:
    }
}
```

**输出:**

```go
fatal error: all goroutines are asleep - deadlock!

goroutine 1 [chan receive]:
main.main()

```

为了避免这种情况，我们在 select 语句中使用了默认情况。或者换句话说，当程序中出现死锁时，执行 select 语句的默认情况以避免死锁。如下例所示，我们在 select 语句中使用了一个默认情况来避免死锁。

**示例:**

```go
// Go program to illustrate how to resolve
// the deadlock problem using the default case
package main

import "fmt"

// Main function
func main() {

    // Creating a channel
    c := make(chan int)
    select {
    case <-c:
    default:
        fmt.Println("!.. Default case..!")
    }
}
```

**输出:**

```go
!.. Default case..!
```

当 select 语句只有零通道时，您也可以使用默认情况。如下例所示，通道 c 为零，所以默认情况下执行如果这里的默认情况不可用，那么程序将永远被阻塞，并出现死锁。

**示例:**

```go
// Go program to illustrate
// the execution of default case
package main

import "fmt"

// Main function
func main() {

    // Creating a channel
    var c chan int

    select {
    case x1 := <-c:
        fmt.Println("Value: ", x1)
    default:
        fmt.Println("Default case..!")
    }
}
```

**输出:**

```go
Default case..!
```