# 戈朗的成分

> 原文:[https://www.geeksforgeeks.org/composition-in-golang/](https://www.geeksforgeeks.org/composition-in-golang/)

组合是一种用来编写可重用代码段的方法。当对象由具有特定行为的其他较小对象组成时，也就是说，具有更广泛功能的较大对象嵌入了具有特定行为的较小对象时，就实现了这一点。组合的最终目标与**继承**的目标相同，但是，这方面的较大对象不是从父类/对象继承特征，而是由其他对象组成，从而可以使用它们的功能。

因为用 Go 语言编写有效的代码主要围绕着使用结构和接口，所以组合是该语言所能提供的一个关键部分。在本文中，我们将讨论通过类型嵌入使用结构和接口的类型组合:

**例 1:** *组成[结构](https://www.geeksforgeeks.org/structures-in-golang/)*

```go
// Golang program to store information
// about games in structs and display them
package main

import "fmt"

// We create a struct details to hold
// generic information about games
type details struct {
    genre       string
    genreRating string
    reviews     string
}

// We create a struct game to hold
// more specific information about
// a particular game
type game struct {

    name  string
    price string
    // We use composition through
    // embedding to add the
    // fields of the details 
    // struct to the game struct
    details
}

// this is a method defined
// on the details struct
func (d details) showDetails() {
    fmt.Println("Genre:", d.genre)
    fmt.Println("Genre Rating:", d.genreRating)
    fmt.Println("Reviews:", d.reviews)
}

// this is a method defined 
// on the game struct
// this method has access 
// to showDetails() as well since
// the game struct is composed
// of the details struct
func (g game) show() {
    fmt.Println("Name: ", g.name)
    fmt.Println("Price:", g.price)
    g.showDetails()
}

func main() {

    // defining a struct 
    // object of Type details
    action := details{"Action","18+", "mostly positive"}

    // defining a struct
    // object of Type game
    newGame := game{"XYZ","$125", action}

    newGame.show()
}
```

**输出:**

```go
Name:  XYZ
Price: $125
Genre: Action
Genre Rating: 18+
Reviews: mostly positive

```

**解释:**在上面的代码片段中，我们创建了两个结构:*细节*和*游戏*。结构*细节*包括游戏的一般信息。结构*游戏*是一个复合结构，有自己的领域，也有*细节*的领域。这种组合是通过类型嵌入实现的，结果是第一个结构变成了一段可重用的代码。

有趣的是，结构*细节*上定义的方法对于*类型游戏*的对象是可访问的，这仅仅是因为*游戏*是由*细节*组成的。

**例 2:** *嵌入[界面](https://www.geeksforgeeks.org/interfaces-in-golang/)* 合成

在 Go 语言中，接口是隐式实现的。也就是说，如果在接口中定义的方法被用在诸如结构这样的对象上，那么该结构就被称为实现了接口。一个接口可以嵌入其他接口，以形成复合接口。如果复合接口中的所有接口都实现了，那么复合接口也被称为是由该对象实现的。

```go
// Golang Program to implement composite interfaces
package main

import "fmt"

type purchase interface {
    sell()
}

type display interface {
    show()
}

// We use the two previous
// interfaces to form
// The following composite 
// interface through embedding
type salesman interface {
    purchase
    display
}

type game struct {
    name, price    string
    gameCollection []string
}

// We use the game struct to
// implement the interfaces
func (t game) sell() {
    fmt.Println("--------------------------------------")
    fmt.Println("Name:", t.name)
    fmt.Println("Price:", t.price)
    fmt.Println("--------------------------------------")
}
func (t game) show() {
    fmt.Println("The Games available are: ")
    for _, name := range t.gameCollection {
        fmt.Println(name)
    }
    fmt.Println("--------------------------------------")
}

// This method takes the composite
// interface as a parameter
// Since the interface is composed
// of purchase and display
// Hence the child methods of those
// interfaces can be accessed here
func shop(s salesman) {
    fmt.Println(s)
    s.sell()
    s.show()
}

func main() {

    collection := []string{"XYZ", 
        "Trial by Code", "Sea of Rubies"}
    game1 := game{"ABC", "$125", collection}
    shop(game1)

}
```

**输出:**

```go
{ABC $125 [XYZ Trial by Code Sea of Rubies]}
--------------------------------------
Name: ABC
Price: $125
--------------------------------------
The Games available are: 
XYZ
Trial by Code
Sea of Rubies
--------------------------------------

```

**说明:**首先我们创建了 2 个界面*购买*和*展示*自带方法原型。然后我们将它们嵌入到界面*业务员*中，以形成一个复合结构。这说明了《围棋》中构图概念的运用。在方法商店()中，我们通过在方法中传递一个 Type game 对象来实现销售员接口。由于这个方法实现了复合接口，我们可以访问最初声明的两个接口的子方法。这样，有效的 go 编程可以通过一个干净的可重用代码来实现。