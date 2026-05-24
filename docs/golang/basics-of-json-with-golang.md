# JSON 与 GoLang 的基础知识

> 原文:[https://www.geeksforgeeks.org/basics-of-json-with-golang/](https://www.geeksforgeeks.org/basics-of-json-with-golang/)

[JSON](https://www.geeksforgeeks.org/javascript-json/) 是一种广泛使用的数据交换格式。Golang 使用**编码/json** 包提供了多种编码和解码 API 来处理 JSON，包括往返于内置和自定义数据类型。

**数据类型:【JSON 解码编码的默认 Golang 数据类型如下:**

*   json 布尔值的 bool
*   JSON 号码的 float64
*   JSON 字符串的字符串
*   JSON 空值为零
*   数组作为 JSON 数组
*   作为 JSON 对象的映射或结构

**1。编码/封送结构:**包*编码/json* 中的封送()函数用于将数据编码成 json。

```go
Syntax: func Marshal(v interface{}) ([]byte, error)

```

**示例:**

```go
// Golang program to illustrate the
// concept of encoding using JSON
package main

import (
    "fmt"
    "encoding/json"
)

// declaring a struct
type Human struct{

    // defining struct variables
    Name string
    Age int
    Address string
}

// main function
func main() {

    // defining a struct instance
    human1 := Human{"Ankit", 23, "New Delhi"}

    // encoding human1 struct
    // into json format
    human_enc, err := json.Marshal(human1)

    if err != nil {

        // if error is not nil
        // print error
        fmt.Println(err)
    }

    // as human_enc is in a byte array
    // format, it needs to be 
    // converted into a string 
    fmt.Println(string(human_enc))

    // converting slices from
    // golang to JSON fomat

    // defining an array
    // of struct instance
    human2 := []Human{
        {Name: "Rahul", Age: 23, Address: "New Delhi"},
        {Name: "Priyanshi", Age: 20, Address: "Pune"},
        {Name: "Shivam", Age: 24, Address: "Bangalore"},
    }

    // encoding into JSON format
    human2_enc, err := json.Marshal(human2)

        if err != nil {

        // if error is not nil
        // print error
            fmt.Println(err)
        }

    // printing encoded array
    fmt.Println()
        fmt.Println(string(human2_enc))
}
```

**输出:**

```go
{"Name":"Ankit", "Age":23, "Address":"New Delhi"}

[{"Name":"Rahul", "Age":23, "Address":"New Delhi"}, {"Name":"Priyanshi", "Age":20, "Address":"Pune"}, {"Name":"Shivam", "Age":24, "Address":"Bangalore"}]

```

**2。解码/解组结构:**包*编码/json* 中的解组()函数用于将 json 中的数据解组或解码为结构。

```go
Syntax: func Unmarshal(data []byte, v interface{}) error

```

**示例:**

```go
// Golang program to illustrate the
// concept of decoding using JSON
package main

import (
    "fmt"
    "encoding/json"
)

// declaring a struct
type Human struct{

    // defining struct variables
    Name string
    Address string
    Age int
}

// main function
func main() {

    // defining a struct instance
    var human1 Human

    // data in JSON format which
    // is to be decoded
    Data := []byte(`{
        "Name": "Deeksha",  
        "Address": "Hyderabad",
        "Age": 21
    }`)

    // decoding human1 struct
    // from json format
    err := json.Unmarshal(Data, &human1)

    if err != nil {

        // if error is not nil
        // print error
            fmt.Println(err)
    }

    // printing details of
    // decoded data 
    fmt.Println("Struct is:", human1)
    fmt.Printf("%s lives in %s.\n", human1.Name, human1.Address)

    // unmarshaling a JSON array
    // to array type in Golang

    // defining an array instance
    // of struct type
    var human2 []Human

    // JSON array to be decoded
    // to an array
    Data2 := []byte(`
    [
        {"Name": "Vani", "Address": "Delhi", "Age": 21},
        {"Name": "Rashi", "Address": "Noida", "Age": 24},
        {"Name": "Rohit", "Address": "Pune", "Age": 25}
    ]`)

    // decoding JSON array to 
    // human2 array
    err2 := json.Unmarshal(Data2, &human2)

        if err2 != nil {

        // if error is not nil
        // print error
            fmt.Println(err2)
        }

    // printing decoded array 
    // values one by one
    for i := range human2{

        fmt.Println(human2[i])
    }
}
```

**输出:**

```go
Struct is: {Deeksha Hyderabad 21}
Deeksha lives in Hyderabad.
{Vani Delhi 21}
{Rashi Noida 24}
{Rohit Pune 25}

```