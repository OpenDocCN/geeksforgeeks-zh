# 戈朗地图

> 原文:[https://www.geeksforgeeks.org/golang-maps/](https://www.geeksforgeeks.org/golang-maps/)

在 Go 语言中，地图是一种强大、巧妙、通用的数据结构。Golang Maps 是无序的键值对的集合。它被广泛使用，因为它提供了快速的查找和值，可以在键的帮助下检索、更新或删除。

*   它是对哈希表的引用。
*   由于它的引用类型，它是廉价的通过，例如，对于 64 位机器，它需要 8 字节，对于 32 位机器，它需要 4 字节。
*   在地图中，一个键必须是唯一的，并且必须是使用 *==* 运算符可比较的类型或支持*的类型！=* 操作员。因此，大多数内置类型可以用作一个键，如 int、float64、符文、字符串、可比数组和结构、指针等。像切片和不可比较的数组和结构这样的数据类型或不可比较的自定义数据类型不用作映射键。
*   在地图中，值不像键一样是唯一的，可以是任何类型，如 int、float64、符文、字符串、指针、引用类型、地图类型等。
*   键的类型和值的类型必须是相同的类型，不允许在相同的映射中有不同类型的键和值。但是键的类型和类型值可以不同。
*   该映射也称为哈希映射、哈希表、无序映射、字典或关联数组。
*   在映射中，您只能在映射初始化时添加值。如果您试图在未初始化的映射中添加值，编译器将会抛出一个错误。

#### 如何创建和初始化地图？

在 Go 语言中，地图可以使用两种不同的方式创建和初始化:

**1。简单:**在此方法中，无需使用 *make()* 功能即可创建和初始化地图:

**创建地图:**您可以使用给定的语法简单地创建一个地图:

```go
// An Empty map
map[Key_Type]Value_Type{}

// Map with key-value pair
map[Key_Type]Value_Type{key1: value1, ..., keyN: valueN}
```

*示例:*

```go
var mymap map[int]string
```

在地图中，地图的零值是零，零地图不包含任何键。如果您试图在 nil 映射中添加一个键值对，那么编译器将抛出运行时错误。
**使用地图文字初始化地图:**地图文字是用数据初始化地图最简单的方法，只需用冒号分隔键值对，最后一个尾随冒号是必要的如果不使用，那么编译器会给出错误。

**示例:**

## 去

```go
// Go program to illustrate how to
// create and initialize maps
package main

import "fmt"

func main() {

    // Creating and initializing empty map
    // Using var keyword
    var map_1 map[int]int

    // Checking if the map is nil or not
    if map_1 == nil {

        fmt.Println("True")
    } else {

        fmt.Println("False")
    }

    // Creating and initializing a map
    // Using shorthand declaration and
    // using map literals
    map_2 := map[int]string{

            90: "Dog",
            91: "Cat",
            92: "Cow",
            93: "Bird",
            94: "Rabbit",
    }

    fmt.Println("Map-2: ", map_2)
}
```

**输出:**

```go
True
Map-2:  map[90:Dog 91:Cat 92:Cow 93:Bird 94:Rabbit]
```

**2。使用 make 函数:**也可以使用 make()函数创建地图。这个函数是一个内置函数，在这个方法中，您只需要传递映射的类型，它就会返回一个初始化的映射。]

**语法:**

```go
make(map[Key_Type]Value_Type, initial_Capacity)
make(map[Key_Type]Value_Type)
```

**示例:**

## 去

```go
// Go program to illustrate how to
// create and initialize a map
// Using make() function
package main

import "fmt"

func main() {

    // Creating a map
    // Using make() function
    var My_map = make(map[float64]string)
    fmt.Println(My_map)

    // As we already know that make() function
    // always returns a map which is initialized
    // So, we can add values in it
    My_map[1.3] = "Rohit"
    My_map[1.5] = "Sumit"
    fmt.Println(My_map)
}
```