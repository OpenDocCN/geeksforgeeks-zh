# 使用结构作为映射键的 Golang 程序

> 原文: [https://www.geeksforgeeks.org/golang-program-that-uses-structs-as-map-keys/](https://www.geeksforgeeks.org/golang-program-that-uses-structs-as-map-keys/)

Go语言中的[**映射（map）**](https://www.geeksforgeeks.org/golang-maps/)是一组无序的键值对的集合。它被广泛使用，因为它提供了快速的查找，值可以在键的帮助下检索、更新或删除。

## 语法:

```go
map[Key_Type]Value_Type{}
```

*示例:* `var sample map[string]int`

这里的`sample`是一个以`string`为键，以`int`类型为值的映射。

在映射中，大多数数据类型都可以用作一个键，如`int`、`string`、`float64`、`rune`等。映射还允许将结构体用作键。这些结构体应该是可比较的。Go语言中的结构体或[**结构**](https://www.geeksforgeeks.org/structures-in-golang/)是用户定义的类型，允许将不同类型的字段组合成一个类型。

## 结构示例:

```go
type Student struct {
      name string 
      rollno int
      class string
      city string
}
```

让我们看看如何在映射中实现一个结构体:

## 例 1:

```go
// Golang program to show how to
// use structs as map keys
package main

// importing required packages
import "fmt"

//declaring a struct
type Address struct {
    Name    string
    city    string
    Pincode int
}

func main() {

// Creating struct instances
    a2 := Address{Name: "Ram", city: "Delhi", Pincode: 2400}
    a1 := Address{"Pam", "Dehradun", 2200}
    a3 := Address{Name: "Sam", city: "Lucknow", Pincode: 1070}

// Declaring a map
    var mp map[Address]int

// Checking if the map is empty or not
    if mp == nil {
        fmt.Println("True")
    } else {
        fmt.Println("False")
    }
    // Declaring and initialising
    // using map literals
    sample := map[Address]int{a1: 1, a2: 2, a3: 3}
    fmt.Println(sample)
}
```

## 输出:

```go
True
map[{Pam Dehradun 2200}:1 {Ram Delhi 2400}:2 {Sam Lucknow 1070}:3]
```

## 迭代映射:

你也可以运行一个循环来访问和操作每个映射键。

## 例 2:

```go
// Golang program to show how to
// use structs as map keys
package main

// importing required packages
import "fmt"

// declaring a struct
type Address struct {
    Name    string
    city    string
    Pincode int
}

func main() {
    // Creating struct instances
    a1 := Address{"Pam", "Mumbai", 2200}
    a2 := Address{Name: "Ram", city: "Delhi", Pincode: 2400}
    a3 := Address{Name: "Sam", city: "Lucknow", Pincode: 1070}

// Declaring and initialising using map literals
    sample := map[Address]int{a1: 1, a2: 2, a3: 3}
    for str, val := range sample {
        fmt.Println(str, val)
    }

// You can also access a struct
    // field while using a loop
    for str := range sample {
        fmt.Println(str.Name)
    }
}
```

## 输出:

```go
{Ram Delhi 2400} 2
{Sam Lucknow 1070} 3
{Pam Mumbai 2200} 1
Pam
Ram
Sam
```

## 在映射中添加键:值对:

在映射中添加键:值对是使用给定的语法完成的:

```go
map_name[struct_instance]=value 
```

如果一个键值对已经存在于映射中，它将用新的键值对更新旧的键值对。

## 例 3:

```go
// Adding key:value pair in a map
package main

// importing required packages
import "fmt"

// declaring a struct
type Student struct {
    Name   string
    rollno int
    course string
}

func main() {

// Creating struct instances
    a1 := Student{"Asha", 1, "CSE"}
    a2 := Student{"Aishwarya", 1, "ECE"}
    a3 := Student{"Priya", 2, "MECH"}

// Declaring and initialising
    // using map literals
    mp := map[Student]int{a1: 1, a2: 2}
    fmt.Println("Original map was", mp)
    mp[a3] = 3
    mp[Student{"Ram", 3, "CSE"}] = 4

// Values have their zero values
    // Here initial value was 0 after 
    // incrementing it became 1
    mp[Student{"Tina", 44, "EEE"}]++

fmt.Println("After adding key:value "+
     "pairs to the map, Updated map is:", mp)
}
```

## 输出:

> 原始地图为地图[{ Aishwarya 1 ECE }:2 { Asha 1 CSE }:1]
> 向地图添加键:值对后，更新后的地图为:地图[{ Aishwarya 1 ECE }:2 { Asha 1 CSE }:1 { Priya 2 MECH }:3 { Ram 3 CSE }:4 { Tina 44 EEE }:1]

## 从映射中删除结构体键:

您可以使用`delete()`函数从映射中删除结构体键。它是一个内置函数，不返回任何值，如果给定的映射中没有该键，则不执行任何操作。其语法如下:

```go
delete(map_name, struct_key)
```

## 例 4:

```go
// Deleting key: value pair in a map
package main

// importing required packages
import "fmt"

// declaring a struct
type Student struct {
    Name   string
    rollno int
    course string
}

func main() {
    // Creating struct instances
    a1 := Student{"Asha", 1, "CSE"}
    a2 := Student{"Aishwarya", 1, "ECE"}
    a3 := Student{"Priya", 2, "MECH"}
    a4 := Student{"Ram", 3, "CSE"}

// Declaring and initialising using map literals
    mp := map[Student]int{a1: 1, a2: 2, a3: 3, a4: 4}

delete(mp, a4)
    fmt.Println("The remaining map after deletion:")
    for str, i := range mp {
        fmt.Println(str, "=", i)
    }

}
```

## 输出:

```go
The remaining map after deletion:
{Asha 1 CSE} = 1
{Aishwarya 1 ECE} = 2
{Priya 2 MECH} = 3
```

## 检查键:值对的存在:

您可以检查映射中是否存在结构体。下面给出了检查映射中是否存在`struct_key`:值对的语法:

> //这给出了值和检查结果
> //如果检查结果为真，则表示密钥存在
> //如果检查结果为假，则表示密钥丢失，在这种情况下，值取零值
> `value, check_variable_name := map_name[key]`
> 
> 或者
> 
> //不带值使用空白标识符
> //只会给出检查结果
> `_, check_variable_name := map_name[key]`

## 例 6:

```go
// Golang program to check if a
// struct key is present
package main

// importing required packages
import "fmt"

// declaring a struct
type Student struct {
    Name   string
    rollno int
    course string
}

func main() {
    // Creating struct instances
    a1 := Student{"Asha", 1, "CSE"}
    a2 := Student{"Aishwarya", 1, "ECE"}
    a3 := Student{"Priya", 2, "MECH"}
    a4 := Student{"Ram", 3, "CSE"}

// Declaring and initialising
    // using map literals
    mp := map[Student]string{a1: "First", 
     a2: "Second", a3: "Third", a4: "Fourth"}

value, check := mp[a4]
    fmt.Println("Is the key present:", check)
    fmt.Println("Value of the key:", value)

_, check2 := mp[a2]
    fmt.Println("Is the key present:", check2)

}
```

## 输出:

```go
Is the key present: true
Value of the key: Fourth
Is the key present: true
```