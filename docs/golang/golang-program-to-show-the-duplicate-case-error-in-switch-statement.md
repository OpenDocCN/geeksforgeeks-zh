# Golang 程序在 Switch 语句中显示重复案例错误

> 原文:[https://www . geesforgeks . org/golang-program-to-show-the-replicate-case-error-in-switch-statement/](https://www.geeksforgeeks.org/golang-program-to-show-the-duplicate-case-error-in-switch-statement/)

A [**开关的**](https://www.geeksforgeeks.org/switch-statement-in-go/) 情况必须有独特的数值。当针对整个开关检查重复值时。出现*“重复案例”*错误。 我们借助例子来讨论重案错误

**例 1:**

## 去

```go
// Golang program that causes 
// duplicate case error

package main

import "fmt"

// Main function
func main() {
    value := 4

    // Duplicate cases are not allowed.
    switch value {
    case 4:
        fmt.Println(true)
    case 4:
        fmt.Println(true)
    }
}
```

**输出:**

```go
./prog.go:15:10: duplicate case 4 in switch
    previous case at ./prog.go:13:10

```

**例 2:**

## 去

```go
// Golang program that causes 
// duplicate case error

package main

import "fmt"

// Main function
func main() {
    i := 1
    switch i {
        case 0, 1:
            fmt.Println("GeeksForGeeks")
            fallthrough
        case 0:
            fmt.Println("Geeks_0")
        case 1:
            fmt.Println("Geeks_1")
        default:
            fmt.Println("Number_of_Users")
    }
}
```

**输出:**

```go
./prog.go:15:8: duplicate case 0 in switch
    previous case at ./prog.go:12:8
./prog.go:17:8: duplicate case 1 in switch
    previous case at ./prog.go:12:11

```