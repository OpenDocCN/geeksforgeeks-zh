# Go语言reflect包中的MapIndex()函数详解

> 原文：[https://www.geeksforgeeks.org/reflect-mapindex-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-mapindex-function-in-golang-with-examples/)

Go语言提供了运行时反射的内置支持实现，并允许程序在`reflect`包的帮助下操作任意类型的对象。`reflect`包中的`MapIndex()`函数用于获取映射`v`中与`key`关联的值。要访问该函数，需要在程序中导入`reflect`包。

## 语法

```go
func (v Value) MapIndex(key Value) Value
```

**参数：** 此函数不接受任何参数。

**返回值：** 该函数返回与映射`v`中的键相关联的值。

以下示例说明了上述方法在Golang中的使用：

## 示例 1

```go
// Golang program to illustrate
// reflect.MapIndex() Function

package main

import (
    "fmt"
    "reflect"
)

func main() {
    test := map[string]interface{}{"First": "firstValue"}
    Pass(test)
}

// Main function
func Pass(d interface{}) {
    mydata := reflect.ValueOf(d).MapIndex(reflect.ValueOf("First"))
    fmt.Printf("Value: %+v \n", mydata.Interface())
    fmt.Printf("Kind: %+v \n", mydata.Kind())
    fmt.Printf("Kind2: %+v \n", reflect.ValueOf(mydata.Interface()).Kind())
}
```

**输出：**

```go
Value: firstValue 
Kind: interface 
Kind2: string
```

## 示例 2

```go
// Golang program to illustrate
// reflect.MapIndex() Function

package main

import (
    "fmt"
    "reflect"
)

type Test struct {
    Data string
}

func (t Test) GetData() string {
    return t.Data
}

type Stringer interface {
    GetData() string
}

// Main function
func main() {
    d := map[string]Stringer{"Geeks": Test{Data: "Null"}}
    mydata := reflect.ValueOf(d).MapIndex(reflect.ValueOf("Geeks"))
    fmt.Println(reflect.ValueOf(mydata.Interface()))
}
```

**输出：**

```go
{Null}
```