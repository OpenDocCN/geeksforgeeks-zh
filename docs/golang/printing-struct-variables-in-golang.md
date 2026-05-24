# 在 Golang 中打印结构变量

> 原文:[https://www . geesforgeks . org/printing-struct-variables-in-golang/](https://www.geeksforgeeks.org/printing-struct-variables-in-golang/)

假设，我们需要打印[结构](https://www.geeksforgeeks.org/structures-in-golang/)及其字段对应的值。我们可以在软件包 **fmt** 的帮助下做到这一点，该软件包使用类似于 C 的 printf 和 scanf 的功能来实现格式化的 I/O。让我们先试试如果我们只是打印结构，会发生什么。

```go
package main

import ("fmt")

// Fields: structure to be printed
type Fields struct {
    Name     string
    NickName string
    Age      int
}

func main() {

    // Initialising the struct with values
    var f = Fields{
    Name:     "Abc",
    NickName: "abc",
    Age:      19,
    }

    // printing the structure
    fmt.Println(f)
}
```

**输出:**

```go
{Abc abc 19}

```

在 Golang 中有两种打印结构变量的方法。第一种方式是使用 **Printf** 函数的包 fmt 在参数中带有特殊的标签打印格式参数。其中一些论点如下:

```go
%v the value in a default format
%+v the plus flag adds field names
%#v a Go-syntax representation of the value

```

```go
package main

import (
    "fmt"
)

// Fields: structure to be printed
type Fields struct {
    Name     string
    NickName string
    Age      int
}

func main() {

    // initializing the 
    // struct with values
    var f = Fields{
        Name:     "Abc",
        NickName: "abc",
        Age:      19,
    }

    // printing the structure
    fmt.Printf("%v\n", f)
    fmt.Printf("%+v\n", f)
    fmt.Printf("%#v\n", f)
}
```

**输出:**

```go
{Abc abc 19}
{Name:Abc NickName:abc Age:19}
main.Fields{Name:"Abc", NickName:"abc", Age:19}

```

带有#v 的 Printf 包括 *main。字段*即结构的名称。它包括“主”来区分不同包装中存在的结构。

**第二种可能的方式**是使用包编码/json 的功能**元帅**。

**语法:**

```go
func Marshal(v interface{}) ([]byte, error)

```

```go
package main

import (
    "encoding/json"
    "fmt"
)

// Fields: structure to be printed
type Fields struct {
    Name     string
    NickName string
    Age      int
}

func main() {

    // initialising the struct
    // with values
    var f = Fields{
        Name:     "Abc",
        NickName: "abc",
        Age:      19,
    }

    // Marshalling the structure
    // For now ignoring error
    // but you should handle
    // the error in above function
    jsonF, _ := json.Marshal(f)

    // typecasting byte array to string
    fmt.Println(string(jsonF))

}
```

**输出:**

```go
{"Name":"Abc", "NickName":"abc", "Age":19}

```