# 戈朗的多态性

> 原文:[https://www.geeksforgeeks.org/polymorphism-in-golang/](https://www.geeksforgeeks.org/polymorphism-in-golang/)

**多态性**是一条消息能够以多种形式显示的能力。多态性被认为是面向对象编程的重要特征之一，可以在运行时或编译时实现。Golang 是一种轻量级面向对象语言，仅通过 [**接口**](https://www.geeksforgeeks.org/interfaces-in-golang/) 支持多态性。让我们先通过下面的例子来理解这些接口:
**例 1:**

## C

```go
// Golang program to illustrate the
// concept of interfaces
package main

import (
    "fmt"
)

// defining an interface
type Figure interface{

    Area() float64
}

// declaring a struct
type Rectangle struct{

    // declaring struct variables
    length float64
    width float64
}

// declaring a struct
type Square struct{

    // declaring struct variable
    side float64
}

// function to calculate
// area of a rectangle
func (rect Rectangle) Area() float64{

    // Area of rectangle = l * b
    area := rect.length * rect.width
    return area
}

// function to calculate
// area of a square
func (sq Square) Area() float64{

    // Area of square = a * a
    area := sq.side * sq.side
    return area
}

// main function
func main() {

    // declaring a rectangle instance
    rectangle := Rectangle{

        length: 10.5,
        width: 12.25,
    }

    // declaring a square instance
    square := Square{

        side: 15.0,
    }

    // printing the calculated result
    fmt.Printf("Area of rectangle: %.3f unit sq.\n", rectangle.Area())
    fmt.Printf("Area of square: %.3f unit sq.\n", square.Area())
}
```

**输出:**

```go
Area of rectangle: 128.625 unit sq.
Area of square: 225.000 unit sq.
```

不同类型的对象以一致的方式对待，只要它们坚持单一的接口，这就是多态的本质。在接口中声明变量属于接口类型。它们可以采用实现接口的任何值，这有助于接口在 Golang 中实现多态性。以下示例解释了多态性的概念:
**示例 2:**

## C

```go
// Golang program to illustrate the
// concept of polymorphism
package main

import (
    "fmt"
)

// defining an interface
type Reading interface{

    // declaring interface method
    reading_time() int
}

// declaring a struct
type Book struct{

    // declaring struct variables
    name string
    page_count int
}

// declaring a struct
type Newspaper struct{

    // declaring struct variables
    name string
    page_count int
}

// declaring a struct
type Magazine struct{

    // declaring struct variables
    name string
    page_count int
}

// function to calculate reading
// time for book
func (book Book) reading_time() int {

    // taking average speed
    // of 10 mins per page
    read_time := 10 * book.page_count
    return read_time
}

// function to calculate reading
// time for newspaper
func (newspaper Newspaper) reading_time() int {

    // taking average speed
    // of 30 mins per page
    read_time := 30 * newspaper.page_count
    return read_time
}

// function to calculate reading
// time for magazine
func (magazine Magazine) reading_time() int {

    // taking average speed
    // of 5 mins per page
    read_time := 5 * magazine.page_count
    return read_time
}

// function to calculate reading time
func calcReadingTime(ReadingTime []Reading) int {

        totalTime := 0

    // looping through elements
    // of the Reading array   
        for _, t := range ReadingTime {

        // run time polymorphism, call to
        // method depends on object being
        // referred at run time
            totalTime += t.reading_time()
        }

        return totalTime
}

// main function
func main() {

    // declaring a book instance
    book1 := Book{
        name: "Goosebumps",
        page_count: 150,
    }

    // declaring a newspaper instance
    newspaper1 := Newspaper{
        name: "TOI",
        page_count: 12,
    }

    // declaring a magazine instance
    magazine1 := Magazine{
        name: "Forbes",
        page_count: 40,
    }

    // array of type Reading interface
    ReadingTime := []Reading{book1, newspaper1, magazine1}

    // total reading time calculated
        totalTime := calcReadingTime(ReadingTime)

    // Printing total time for reading
        fmt.Printf("Total Time is %d minutes.\n", totalTime)
}
```

**输出:**

```go
Total Time is 2060 minutes.
```