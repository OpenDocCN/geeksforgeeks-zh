# Golang 程序在结构类型定义中使用字段标签

> 原文:[https://www . geesforgeks . org/golang-程序使用字段-结构类型定义中的标签/](https://www.geeksforgeeks.org/golang-program-to-use-field-tags-in-the-definition-of-struct-type/)

[Golang 中的结构](https://www.geeksforgeeks.org/structures-in-golang/)用于在一个地方存储不同类型的数据。“struct”本身是用户定义的数据类型。Golang 中“struct”的语法如下:

**语法:**

```go
type var_name struct
{
     var1  data_type
     var2  data_type
}

```

Golang 中的结构被写到像 JSON 这样的文件中。它是一种数据存储格式。Golang 在标准库中提供包，用于向/从 JSON 文件中写入和检索结构。在结构的定义中，**字段标签**被添加到字段声明中，作为 JSON 文件中的字段名。

**语法:**

```go
type Book struct 
{
    Name    string  `json:"name"`
    Author  string  `json: "author"`
    Price   int     `json: "price"`
}

```

下面的程序说明了在 Golang 的结构类型定义中字段标签的使用:

**程序 1:**

```go
// Golang program to show how to use
// field tags in the definition of Struct
package main

import 
(
    "encoding/json"
    "fmt"
)

type Book struct 
{
    Name    string  `json:"name"`
    Author  string  `json: "author"`
    Price   int     `json: "price"`
}

func main() {

    var b Book

    b.Name = "DBMS"
    b.Author = "Navathe"
    b.Price = 850

    fmt.Println(b)

    // returns []byte which is b in JSON form.
    jsonStr, err := json.Marshal(b)
    if err != nil {
        fmt.Println(err.Error())
    }

    fmt.Println(string(jsonStr))
}
```

**输出:**

```go
{DBMS Navathe 850}
{"name":"DBMS", "author":"Navathe", "price":850}

```

**程序 2:**

```go
// Golang program to show how to use
// field tags in the definition of Struct
package main

import 
(
    "encoding/json"
    "fmt"
)

type Fruit struct 
{
    Name    string  `json:"name"`
    Quantity  string  `json: "quantity"`
    Price   int     `json: "price"`
}

func main() {

    var f Fruit

    f.Name = "Apple"
    f.Quantity = "2KG"
    f.Price = 100

    fmt.Println(f)

    // returns []byte which is f in JSON form.
    jsonStr, err := json.Marshal(f)
    if err != nil {
        fmt.Println(err.Error())
    }

    fmt.Println(string(jsonStr))
}
```

**输出:**

```go
{Apple 2KG 100}
{"name":"Apple", "quantity":"2KG", "price":100}

```