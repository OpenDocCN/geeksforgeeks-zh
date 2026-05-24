# 格朗的方法

> 原文:[https://www.geeksforgeeks.org/methods-in-golang/](https://www.geeksforgeeks.org/methods-in-golang/)

Go 语言支持方法。Go 方法类似于 Go 函数，但有一点不同，即该方法包含一个接收器参数。在接收器参数的帮助下，该方法可以访问接收器的属性。这里，接收器可以是结构类型或非结构类型。在代码中创建方法时，接收器和接收器类型必须存在于同一个包中。并且不允许创建这样的方法，其中接收者类型已经在另一个包中定义，包括像 int、string 等内置类型。如果你试图这样做，那么编译器会给出一个错误。

**语法:**

```go
func(reciver_name Type) method_name(parameter_list)(return_type){
// Code
}
```

这里，可以在方法中访问接收器。

#### 具有结构类型接收器的方法

在 Go 语言中，您可以定义一个方法，该方法的接收器是结构类型的。该接收器可在方法内部访问，如下例所示:

**示例:**

## 去

```go
// Go program to illustrate the
// method with struct type receiver
package main

import "fmt"

// Author structure
type author struct {
    name      string
    branch    string
    particles int
    salary    int
}

// Method with a receiver
// of author type
func (a author) show() {

    fmt.Println("Author's Name: ", a.name)
    fmt.Println("Branch Name: ", a.branch)
    fmt.Println("Published articles: ", a.particles)
    fmt.Println("Salary: ", a.salary)
}

// Main function
func main() {

    // Initializing the values
    // of the author structure
    res := author{
        name:      "Sona",
        branch:    "CSE",
        particles: 203,
        salary:    34000,
    }

    // Calling the method
    res.show()
}
```

**输出:**

```go
Author's Name:  Sona
Branch Name:  CSE
Published articles:  203
Salary:  34000
```

#### 具有非结构类型接收器的方法

在 Go 语言中，只要类型和方法定义存在于同一个包中，您就可以创建具有非结构类型接收器的方法。如果它们出现在不同的包中，如 int、string 等，那么编译器会给出一个错误，因为它们是在不同的包中定义的。

**例:**

## Go

```go
// Go program to illustrate the method
// with non-struct type receiver
package main

import "fmt"

// Type definition
type data int

// Defining a method with
// non-struct type receiver
func (d1 data) multiply(d2 data) data {
    return d1 * d2
}

/*
// if you try to run this code,
// then compiler will throw an error
func(d1 int)multiply(d2 int)int{
return d1 * d2
}
*/

// Main function
func main() {
    value1 := data(23)
    value2 := data(20)
    res := value1.multiply(value2)
    fmt.Println("Final result: ", res)
}
```

**输出:**

```go
Final result:  460
```

#### 指针接收器的方法

在围棋语言中，你可以创建一个带有 [**指针**](https://www.geeksforgeeks.org/pointers-in-golang/) 接收器的方法。在指针接收器的帮助下，如果在方法中进行了更改，它将反映在调用者中，这对于值接收器方法是不可能的。

**语法:**

```go
func (p *Type) method_name(...Type) Type {
// Code
}
```

**例:**

## Go

```go
// Go program to illustrate pointer receiver
package main

import "fmt"

// Author structure
type author struct {
    name      string
    branch    string
    particles int
}

// Method with a receiver of author type
func (a *author) show(abranch string) {
    (*a).branch = abranch
}

// Main function
func main() {

    // Initializing the values
    // of the author structure
    res := author{
        name:   "Sona",
        branch: "CSE",
    }

    fmt.Println("Author's name: ", res.name)
    fmt.Println("Branch Name(Before): ", res.branch)

    // Creating a pointer
    p := &res

    // Calling the show method
    p.show("ECE")
    fmt.Println("Author's name: ", res.name)
    fmt.Println("Branch Name(After): ", res.branch)
}
```

**输出:**

```go
Author's name:  Sona
Branch Name(Before):  CSE
Author's name:  Sona
Branch Name(After):  ECE
```

#### 方法可以接受指针和值

我们知道，在 Go 中，当一个函数有一个值参数时，它将只接受参数的值，如果你试图传递一个指向值函数的指针，那么它将不会接受，反之亦然。但是一个 Go 方法可以接受值和指针，不管它是用指针还是值接收器定义的。如下例所示:

**例:**

## Go

```go
// Go program to illustrate how the
// method can accept pointer and value

package main

import "fmt"

// Author structure
type author struct {
    name   string
    branch string
}

// Method with a pointer
// receiver of author type
func (a *author) show_1(abranch string) {
    (*a).branch = abranch
}

// Method with a value
// receiver of author type
func (a author) show_2() {

    a.name = "Gourav"
    fmt.Println("Author's name(Before) : ", a.name)
}

// Main function
func main() {

    // Initializing the values
    // of the author structure
    res := author{
        name:   "Sona",
        branch: "CSE",
    }

    fmt.Println("Branch Name(Before): ", res.branch)

    // Calling the show_1 method
    // (pointer method) with value
    res.show_1("ECE")
    fmt.Println("Branch Name(After): ", res.branch)

    // Calling the show_2 method
    // (value method) with a pointer
    (&res).show_2()
    fmt.Println("Author's name(After): ", res.name)
}
```

**输出:**

```go
Branch Name(Before):  CSE
Branch Name(After):  ECE
Author's name(Before) :  Gourav
Author's name(After):  Sona
```

#### 方法与功能的区别

<figure class="table">

| 方法 | 功能 |
| --- | --- |
| 它包含一个接收器。 | 它不包含接收器。 |
| 程序中可以定义同名但不同类型的方法。 | 程序中不允许定义同名不同类型的函数。 |
| 不能作为一阶对象。 | 可以作为一阶对象，可以通过 |

</figure>