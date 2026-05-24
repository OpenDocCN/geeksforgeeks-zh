# Go 关键词

> 原文:[https://www.geeksforgeeks.org/go-keywords/](https://www.geeksforgeeks.org/go-keywords/)

关键字或保留字是语言中用于某些内部过程或代表某些预定义操作的字。因此，不允许将这些单词用作标识符。这样做会导致编译时错误。

**示例:**

```go
// Go program to illustrate the
// use of keywords
package main
import "fmt"

// Here, package, import, func,
// var are keywords
func main() {

// Here, a is a valid identifier
var a = "GeeksforGeeks" 

fmt.Println(a)

// Here, the default is an
// illegal identifier and
// compiler will throw an error
// var default = "GFG"
}
```

**输出:**

```go
GeeksforGeeks
```

围棋语言共有 ***共 25 个关键词*** 如下:

| 破裂 |
| 情况 |
| 陈 |
| 常数 |
| 继续 |

| 系统默认值 |
| 推迟 |
| 其他 |
| 失败 |
| 为 |

| 功能 |
| 去 |
| 转到 |
| 如果 |
| 进口 |

| 连接 |
| 地图 |
| 包裹 |
| 范围 |
| 返回 |

| 挑选 |
| 结构体 |
| 转换 |
| 类型 |
| 定义变量 |

**示例:**

```go
// Go program to illustrate 
// the use of keywords

// Here package keyword is used to 
// include main package in the program
package main

// import keyword is used to 
// import "fmt" in your package
import "fmt"

// func is used to
// create function
func main() {

    // Here, var keyword is used 
    // to create variables
    // Pname, Lname, and Cname 
    // are the valid identifiers
    var Pname = "GeeksforGeeks" 
    var Lname = "Go Language" 
    var Cname = "Keywords"

    fmt.Printf("Portal name: %s", Pname)
    fmt.Printf("\nLanguage name: %s", Lname)
    fmt.Printf("\nChapter name: %s", Cname)

}
```

**输出:**

```go
Portal name: GeeksforGeeks
Language name: Go Language
Chapter name: Keywords

```