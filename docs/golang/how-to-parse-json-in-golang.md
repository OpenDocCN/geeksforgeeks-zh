# 如何解析 Golang 中的 JSON？

> 原文:[https://www.geeksforgeeks.org/how-to-parse-json-in-golang/](https://www.geeksforgeeks.org/how-to-parse-json-in-golang/)

Golang 提供了多个 API 来使用 [JSON](https://www.geeksforgeeks.org/json-full-form/) 工作，包括使用**编码/json** 包往返于内置和自定义数据类型。为了解析 json，我们使用包编码/json 中的**解组()**函数将 JSON 中的数据解包或解码为[结构](https://www.geeksforgeeks.org/structures-in-golang/)。

```go
Syntax: func Unmarshal(data []byte, v interface{}) error

```

解组解析 JSON 编码的数据，并将结果存储在 v 指向的值中。

**注意:**如果 v 为零或者不是指针，解组将返回**无效解组错误。**

**例 1:**

```go
// Golang program to illustrate the
// concept of parsing json to struct
package main

import (
    "encoding/json"
    "fmt"
)

// declaring a struct
type Country struct {

    // defining struct variables
    Name      string
    Capital   string
    Continent string
}

// main function
func main() {

    // defining a struct instance
    var country1 Country

    // data in JSON format which
    // is to be decoded
    Data := []byte(`{
        "Name": "India",  
        "Capital": "New Delhi",
        "Continent": "Asia"
    }`)

    // decoding country1 struct
    // from json format
    err := json.Unmarshal(Data, &country1)

    if err != nil {

        // if error is not nil
        // print error
        fmt.Println(err)
    }

    // printing details of
    // decoded data
    fmt.Println("Struct is:", country1)
    fmt.Printf("%s's capital is %s and it is in %s.\n", country1.Name, 
                                 country1.Capital, country1.Continent)
}
```

**输出:**

```go
Struct is: {India New Delhi Asia}
India's capital is New Delhi and it is in Asia.

```

**例 2:**

```go
// Golang program to illustrate the
// concept of parsing JSON to an array
package main

import (
    "encoding/json"
    "fmt"
)

// declaring a struct
type Country struct {

    // defining struct variables
    Name      string
    Capital   string
    Continent string
}

// main function
func main() {

    // defining a struct instance
    var country []Country

    // JSON array to be decoded
    // to an array in golang
    Data := []byte(`
    [
        {"Name": "Japan", "Capital": "Tokyo", "Continent": "Asia"},
        {"Name": "Germany", "Capital": "Berlin", "Continent": "Europe"},
        {"Name": "Greece", "Capital": "Athens", "Continent": "Europe"},
        {"Name": "Israel", "Capital": "Jerusalem", "Continent": "Asia"}
    ]`)

    // decoding JSON array to
    // the country array
    err := json.Unmarshal(Data, &country)

    if err != nil {

        // if error is not nil
        // print error
        fmt.Println(err)
    }

    // printing decoded array
    // values one by one
    for i := range country {
        fmt.Println(country[i].Name + " - " + country[i].Capital + 
                                     " - " + country[i].Continent)
    }
}
```

**输出:**

```go
Japan - Tokyo - Asia
Germany - Berlin - Europe
Greece - Athens - Europe
Israel - Jerusalem - Asia

```