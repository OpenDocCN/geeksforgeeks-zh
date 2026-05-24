# 如何在 Golang 中使用结构文字创建结构实例？

> 原文:[https://www . geesforgeks . org/how-to-create-a-struct-instance-use-a-struct-literal-in-golang/](https://www.geeksforgeeks.org/how-to-create-a-struct-instance-using-a-struct-literal-in-golang/)

Golang 中的结构或 [**结构**](https://www.geeksforgeeks.org/structures-in-golang/) 是用户定义的数据类型，是各种数据字段的组合。每个数据字段都有自己的数据类型，可以是内置的，也可以是其他用户定义的类型。Struct 表示任何具有一组属性/字段的现实实体。

例如，一个学生有名字、学号、城市、系。将这四个属性分组到一个结构地址中是有意义的，如下所示。

```go
type Student struct {
      name string 
      roll_no int
      city string
      department string
}

```

**声明结构的语法:**

```go
var x Student
```

上面的代码创建了一个 Student 类型的变量，其中字段默认设置为各自的 [**零值**](https://www.geeksforgeeks.org/zero-value-in-golang/) 。

由于 struct 是一种复合数据类型，因此它是使用[复合文字](https://golang.org/ref/spec#Composite_literals)初始化的。复合文字为结构、数组、切片和映射构造值，其中这些类型使用单一语法。结构文字用于在 Golang 中创建结构实例。您可以使用结构文字创建结构实例，如下所示:

```go
var d = Student{"Akshay", 1, "Lucknow", "Computer Science"}
```

我们也可以使用[短声明](https://www.geeksforgeeks.org/short-variable-declaration-operator-in-go/)运算符。

```go
d := Student{"Akshay", 1, "Lucknow", "Computer Science"} 
```

创建结构文字时，必须牢记以下规则:

1.  The key must be a field name declared in the structure type.
2.  The list of elements without any key must list one element for each structure field in the order of field declaration.
3.  The list of elements containing keys does not need to have an element for each structure field. The omitted field gets the zero value of the field.
4.  Text can omit the list of elements; The calculated result of this kind of text is the zero value of its type.
5.  It is wrong to specify elements for non-exported fields belonging to structures of different packages.

**例 1:**

```go
// Golang program to show how to
// declare and define the struct
// using struct literal
package main

// importing required modules
import "fmt"

// Defining a struct type
type Student struct {
    name       string
    roll_no    int
    city       string
    department string
}

func main() {

    // Declaring a variable of a `struct` type
    // All the struct fields are initialized
    // with their zero value
    var x Student
    fmt.Println("Student0:", x)

    // Declaring and initializing a
    // struct using a struct literal
    // Fields should be initialised in
    // the same order as they are declared
    // in struct's definition
    x1 := Student{"Akshay", 1, "Lucknow", "Computer Science"}

    fmt.Println("Student1: ", x1)

    // You can specify keys for 
    // their respective values
    x2 := Student{name: "Anita", roll_no: 2, 
     city: "Ballia", department: "Mechanical"}

    fmt.Println("Student2: ", x2)
}
```

**输出:**

```go
Student0: { 0  }
Student1:  {Akshay 1 Lucknow Computer Science}
Student2:  {Anita 2 Ballia Mechanical}

```

未初始化的字段被设置为它们相应的零值。

**例 2:**

```go
// Golang program illustrating
// the use of string literals
package main

// importing required modules
import "fmt"

// Defining a struct type
type Address struct {
    name, city string
    Pincode    int
}

func main() {
    add1 := Address{name: "Ram"}
    fmt.Println("Address is:", add1)
}
```

**输出:**

```go
Address is: {Ram  0}
```

必须注意的是，在实例化过程中使用*字段:值*初始化器时，未初始化的值被设置为零值。下面的代码将输出一个错误。

**例:**

```go
// Golang program illustrating
// the use of string literals
package main

// importing required modules
import "fmt"

// Defining a struct type
type Address struct {
    name, city string
    Pincode    int
}

func main() {
    add1 := Address{"Ram"}
    fmt.Println("Address is: ", add1)
}
```

**输出:**

```go
Compilation Error: too few values in Address literal
```

如果您为一个元素指定了至少一个键，那么您也必须指定所有其他键。

**例:**

```go
package main

// importing required modules
import "fmt"

// Defining a struct type
type Address struct {
    name, city string
    Pincode    int
}

func main() {
    // Only 1 key is specified here
    add1 := Address{name: "Ram", "Mumbai", 221007}
    fmt.Println("Address is: ", add1)
}
```

**输出:**

```go
Compilation Error: mixture of field:value and value initializers
```

上面的程序抛出了一个错误，因为我们只为一个元素指定了键，这就产生了*字段:值*和值初始化器的混合。我们应该使用*字段:值*或者值初始值设定项。