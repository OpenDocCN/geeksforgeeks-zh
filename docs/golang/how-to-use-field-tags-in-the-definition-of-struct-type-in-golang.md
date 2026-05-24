# 如何在 Golang 的结构类型定义中使用字段标签？

> 原文:[https://www . geesforgeks . org/如何使用 golang 中结构类型定义中的字段标签/](https://www.geeksforgeeks.org/how-to-use-field-tags-in-the-definition-of-struct-type-in-golang/)

Golang 为自定义数据类型的定义提供了[结构](https://www.geeksforgeeks.org/structures-in-golang/)。Go 中的结构概念类似于 C/C++中的结构。

**示例:**

```go
type Person struct {
    Name    string
    Aadhar   int
    Street  string
    HouseNo int
}

```

Golang 中的结构可以被写入像 JSON 这样的文件，用于在硬盘上存储数据或通过网络发送。JSON 是一种轻量级的数据存储格式。Go 提供标准库中的包，用于将结构写入 JSON 文件和从 JSON 文件中检索结构。

在定义结构的过程中，**额外的称为字段标记的原始字符串值**可以添加到字段声明中，该字段声明在 JSON 文件中用作字段名。如果没有指定额外的字符串值，即字段标记，Go 将使用默认字段名称，该名称用于在结构中声明字段。

**带字段标签的结构定义:**

```go
type Person struct {
    Name    string `json:"name"`
    Aadhar  int    `json: "aadhar"`
    Street  string `json: "street"`
    HouseNo int    `json: "house_number"`
}

```

**注意:**如果要在 JSON 中存储结构，字段名必须以大写字母开头。

```go
// Golang program to show how to use Field
// Tags in the Definition of Struct Type
package main

import (
    "encoding/json"
    "fmt"
)

type Person struct {
    Name    string `json:"name"`         // field tag for Name
    Aadhar  int    `json:"aadhar"`       // field tag for Aadhar
    Street  string `json:"street"`       // field tag for Street
    HouseNo int    `json:"house_number"` // field tag for HouseNO
}

func main() {

    var p Person

    p.Name = "ABCD"
    p.Aadhar = 1234123412341234
    p.Street = "XYZ"
    p.HouseNo = 10

    fmt.Println(p)

    // returns []byte which is p in JSON form.
    jsonStr, err := json.Marshal(p)
    if err != nil {
        fmt.Println(err.Error())
    }

    fmt.Println(string(jsonStr))

    // Sample JSON data
    var str = `{ 
        "name" : "PQRX",
        "aadhar" : 1234123412341234,
        "street" : "XYZW",
        "house_number" : 10
    }`

    var p2 Person

    // retains values of fields from JSON string
    err = json.Unmarshal([]byte(str), &p2)
    // and stores it into p2
    if err != nil {
        fmt.Println(err.Error())
    }

    fmt.Println(p2)
}
```

**输出:**

```go
{ABCD 1234123412341234 XYZ 10}
{"name":"ABCD","aadhar":1234123412341234,"street":"XYZ","house_number":10}
{PQRX 1234123412341234 XYZW 10}

```