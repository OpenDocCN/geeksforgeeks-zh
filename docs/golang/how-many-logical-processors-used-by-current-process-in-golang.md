# Golang 当前进程使用了多少个逻辑处理器？

> 原文:[https://www . geeksforgeeks . org/golang 当前进程使用了多少个逻辑处理器/](https://www.geeksforgeeks.org/how-many-logical-processors-used-by-current-process-in-golang/)

任务是找到进程在给定时间可以运行的逻辑处理器的数量。以下是几个例子。

**方法 1:使用** **umCPU 功能**

NumCPU 返回当前进程可用的逻辑 CPU 数量。

**语法:**

```go
func NumCPU() int

```

**示例:**

## 去

```go
// Golang program to find the 
// number of logical processors
// used by current process

package main

import (
    "fmt"
    "runtime"
)

// Main function
func main() {

    // Using the NumCPU function
    fmt.Println(runtime.NumCPU())
}
```

**输出:**

```go
8

```

**方法 2:使用****gomaxpros****功能**

**GOMAXPROCS** 设置可以同时执行的最大 CPU 数，并返回之前的设置。

**语法:**

```go
func GOMAXPROCS(n int) int

```

**示例:**

## 去

```go
// Golang program to find the 
// number of logical processors
// used by current process

package main

import (
    "fmt"
    "runtime"
)

// Main function
func main() {

    // Using the GOMAXPROCS function
    fmt.Println(runtime.GOMAXPROCS(0))
}
```

**输出:**

```go
8

```