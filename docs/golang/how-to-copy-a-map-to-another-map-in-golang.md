# 如何在 Golang 将一张地图复制到另一张地图？

> 原文:[https://www . geeksforgeeks . org/如何将一幅地图复制到另一幅地图中 golang/](https://www.geeksforgeeks.org/how-to-copy-a-map-to-another-map-in-golang/)

**[Golang 中的地图](https://www.geeksforgeeks.org/golang-maps/)** 是无序的键值对的集合。它被广泛使用，因为它提供了快速的查找和值，可以在键的帮助下检索、更新或删除。在地图中，您可以使用 Go 语言提供的 **for loop** 将地图复制到另一张地图。在 for 循环中，我们用元素获取索引值 1 乘 1，并将其分配给另一个映射。

**语法:**

```go
for key, value := range originalMap{
}

```

让我们借助例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate how to 
// copy a map to another map 

package main 

import "fmt"

func main() { 

    // Creating and initializing a map 
    // Using shorthand declaration and 
    // using map literals 
    originalMap := make(map[string]int)
    originalMap["one"] = 1
    originalMap["two"] = 2
    originalMap["three"] = 3
    originalMap["four"] = 4
    originalMap["five"] = 5
    originalMap["six"] = 6
    originalMap["seven"] = 7
    originalMap["eight"] = 8
    originalMap["nine"] = 9

    // Creating empty map 
    CopiedMap:= make(map[string]int)

    /* Copy Content from Map1 to Map2*/
    for index, element  := range originalMap{        
         CopiedMap[index] = element
    }

    for index, element  := range CopiedMap{ 
        fmt.Println(index, "=>", element)  
    }
}
```

**输出:**

```go
seven => 7
eight => 8
two => 2
four => 4
three => 3
six => 6
nine => 9
one => 1
five => 5

```

**例 2:**

```go
// Go program to illustrate how to 
// copy a map to another map 

package main 

import "fmt"

func main() { 

    // Creating and initializing a map 
    // Using shorthand declaration and 
    // using map literals 
    map_1 := map[int]string{ 

            90: "Dog", 
            91: "Cat", 
            92: "Cow", 
            93: "Bird", 
            94: "Rabbit", 
    } 

    // Creating and initializing empty map 
    map2 := map[string]int{} 

    /* Copy Content from Map1 to Map2*/
    for key, value := range map_1{        
         map2[value] = key
    }

    fmt.Println("Copied Map :", map2) 
}
```

**输出:**

```go
Copied Map : map[Bird:93 Rabbit:94 Dog:90 Cat:91 Cow:92]

```