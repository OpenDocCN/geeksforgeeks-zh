# 如何给 Golang 中的结构字段赋值？

> 原文:[https://www . geesforgeks . org/如何为 golang 中的结构字段分配默认值/](https://www.geeksforgeeks.org/how-to-assign-default-value-for-struct-field-in-golang/)

默认值可以通过使用构造函数分配给结构。我们可以使用构造函数为其所有或部分成员分配自定义默认值，而不是直接创建结构。

**例 1:**

```go
// Golang program to assign
// default values to a struct 
// using constructor function
package main

import (
    "fmt"
)

// declaring a student struct
type Student struct{

    // declaring struct variables
    name string
    marks int64
    age int64
}

// constructor function
func(std *Student) fill_defaults(){

    // setting default values
    // if no values present
    if std.name == "" {
        std.name = "ABC"
    }

    if std.marks == 0 {
        std.marks = 40
    }

    if std.age == 0 {
        std.age = 18
    }
}

// main function
func main() {

    // creating a struct where
    // only the name is initialised
    std1 := Student{name: "Vani"}

    // printing the struct 
    // with no default values
    fmt.Println(std1)

    // this will assign default values 
    // to non-initialised valiables
    // in struct std1
    std1.fill_defaults()

    // printing after assigning
    // defaults to struct variables
    fmt.Println(std1)

    // creating a struct where
    // age and marks are initialised
    std2 := Student{age: 19, marks: 78}

    // assigning default name
    std2.fill_defaults()

    // printing after assigning 
    // default name to struct
    fmt.Println(std2)

}
```

**输出:**

```go
{Vani 0 0}
{Vani 40 18}
{ABC 78 19}

```

向结构分配默认值的另一种方法是使用标记。标记只能用于字符串值，并且可以通过使用单引号(")来实现。

**例 2:**

```go
// Golang program to assign
// default values to a struct 
// using tags

package main

import (
    "fmt"
    "reflect"
)

// declaring a person struct
type Person struct {

    // setting the default value 
    // of name to "geek"
      name string `default:"geek"` 

}

func default_tag(p Person) string {

    // TypeOf returns type of 
    // interface value passed to it
      typ := reflect.TypeOf(p)

    // checking if null string
      if p.name == "" {

        // returns the struct field 
        // with the given parameter "name"
            f, _ := typ.FieldByName("name")

        // returns the value associated 
        // with key in the tag string
        // and returns empty string if 
        // no such key in tag
            p.name = f.Tag.Get("default")
      }

      return fmt.Sprintf("%s", p.name)
}

// main function
func main(){

    // prints out the default name 
    fmt.Println("Default name is:", default_tag(Person{}))
}
```

**输出:**

```go
Default name is: geek

```