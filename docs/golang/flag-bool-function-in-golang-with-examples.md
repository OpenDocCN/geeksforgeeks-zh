# 旗。Golang 中的 Bool()函数示例

> 原文:[https://www . geesforgeks . org/flag-bool-function-in-golang-with-examples/](https://www.geeksforgeeks.org/flag-bool-function-in-golang-with-examples/)

Go 语言提供了对命令行解析的内置支持，并具有可用于定义与使用`flag`包的命令行程序一起使用的标志的功能。该包提供**标志。Bool()** 函数，用于定义具有指定名称、默认值和用法字符串的布尔标志。

**语法:**

```go
func Bool(name string, value bool, usage string) *bool
```

**参数:**该功能接受三个参数，如上所述，描述如下:

*   **名称:**它是一个字符串，指定用于标志的名称。
*   **值:**是一个布尔值，指定标志使用的默认值。
*   **用法:**它是一个字符串，指定要为标志显示的用法或帮助消息。

**返回值:**返回存储已定义标志值的布尔变量的地址。

下面的程序说明了**标志。Bool()** 功能:

**例 1:**

```go
// Golang program to illustrate
// the flag.Bool() Function
package main

import (
    "flag"
    "fmt"
)

func main() {
    // Define a bool flag
    boolArgPtr := flag.Bool("arg1", false, "This is a bool argument")

    // Parse command line 
    // into the defined flags
    flag.Parse()

    fmt.Println("Bool Arg:", *boolArgPtr)
}
```

**输出:**

*   **指定标志值**

    ```go
    $ go run ex1.go -arg1=true
    Bool Arg: true
    ```

*   **不指定标志值(默认值)**

    ```go
    $ go run ex1.go
    Bool Arg: false

    ```

**例 2:**

```go
// Golang program to illustrate
// the flag.Bool() Function
package main

import (
    "flag"
    "fmt"
)

func main() {

    // Define multiple bool arguments
    plainArgPtr := flag.Bool("plaintext", false, "Enable plaintext")
    jsonArgPtr := flag.Bool("json", false, "Enable JSON")
    csvArgPtr := flag.Bool("csv", false, "Enable CSV")

    // Parse command line into the defined flags
    flag.Parse()

    fmt.Println("Enable plaintext:", *plainArgPtr)
    fmt.Println("Enable JSON:", *jsonArgPtr)
    fmt.Println("Enable CSV:", *csvArgPtr)
}
```

**输出**

*   **指定一些标志值**

    ```go
    $ go run ex2.go -plaintext=true -csv=true
    Enable plaintext: true
    Enable JSON: false
    Enable CSV: true

    ```

*   **不指定任何标志值(默认值)**

    ```go
    $ go run ex2.go
    Enable plaintext: false
    Enable JSON: false
    Enable CSV: false

    ```