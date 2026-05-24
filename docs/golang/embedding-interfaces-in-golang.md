# 在 Golang 中嵌入接口

> 原文:[https://www . geesforgeks . org/embedding-interfaces-in-golang/](https://www.geeksforgeeks.org/embedding-interfaces-in-golang/)

在 Go 语言中，接口是方法签名的集合，它也是一种类型，意味着您可以创建一个接口类型的变量。我们知道 Go 语言不支持继承，但是 Go 接口完全支持嵌入。在嵌入中，一个接口可以嵌入其他接口，或者一个接口可以在其中嵌入其他接口的方法签名，两者的结果与示例 1 和示例 2 所示相同。您可以在单个接口中嵌入任意数量的接口。当一个接口嵌入其他接口时，如果我们对接口的方法做了任何更改，那么它也会反映在嵌入的接口中，如示例 3 所示。

**语法:**

```go
type interface_name1 interface {

    Method1()
}

type interface_name2 interface {

    Method2()
}

type finalinterface_name interface {

    interface_name1
    interface_name2
}

or

type interface_name1 interface {

    Method1()
}

type interface_name2 interface {

    Method2()
}

type finalinterface_name interface {

    Method1()
    Method2()
}

```

**例 1:**

```go
// Go program to illustrate the concept
// of the embedding interfaces
package main

import "fmt"

// Interface 1
type AuthorDetails interface {

    details()
}

// Interface 2
type AuthorArticles interface {

    articles()
}

// Interface 3

// Interface 3 embedded with
// interface 1 and 2
type FinalDetails interface {

    AuthorDetails
    AuthorArticles
}

// Structure
type author struct {

    a_name    string
    branch    string
    college   string
    year      int
    salary    int
    particles int
    tarticles int
}

// Implementing method of 
// the interface 1
func (a author) details() {

    fmt.Printf("Author Name: %s", a.a_name)
    fmt.Printf("\nBranch: %s and passing year: %d",
                                  a.branch, a.year)
    fmt.Printf("\nCollege Name: %s", a.college)
    fmt.Printf("\nSalary: %d", a.salary)
    fmt.Printf("\nPublished articles: %d", a.particles)
}

// Implementing method 
// of the interface 2
func (a author) articles() {

    pendingarticles := a.tarticles - a.particles
    fmt.Printf("\nPending articles: %d", pendingarticles)
}

// Main value
func main() {

    // Assigning values
    // to the structure
    values := author{
        a_name:    "Mickey",
        branch:    "Computer science",
        college:   "XYZ",
        year:      2012,
        salary:    50000,
        particles: 209,
        tarticles: 309,
    }

    // Accessing the methods of 
    // the interface 1 and 2
    // Using FinalDetails interface
    var f FinalDetails = values
    f.details()
    f.articles()
}
```

**输出:**

```go
Author Name: Mickey
Branch: Computer science and passing year: 2012
College Name: XYZ
Salary: 50000
Published articles: 209
Pending articles: 100

```

**说明:**如上例所示，我们有三个接口。接口 1 和 2 是简单的接口，接口 3 是嵌入式接口，其中包含 1 和 2 接口。因此，如果接口 1 和接口 2 发生任何变化，都会反映在接口 3 中。接口 3 可以访问接口 1 和 2 中的所有方法。

**例 2:**

```go
// Go program to illustrate the
// concept of embedding interfaces
package main

import "fmt"

// Interface 1
type AuthorDetails interface {
    details()
}

// Interface 2
type AuthorArticles interface {
    articles()
}

// Interface 3

// Interface 3 embedded with 
// interface 1 and 2's methods
type FinalDetails interface {

    details()
    articles()
}

// Structure
type author struct {

    a_name    string
    branch    string
    college   string
    year      int
    salary    int
    particles int
    tarticles int
}

// Implementing method of
// the interface 1
func (a author) details() {

    fmt.Printf("Author Name: %s", a.a_name)
    fmt.Printf("\nBranch: %s and passing year: %d", a.branch, a.year)
    fmt.Printf("\nCollege Name: %s", a.college)
    fmt.Printf("\nSalary: %d", a.salary)
    fmt.Printf("\nPublished articles: %d", a.particles)
}

// Implementing method 
// of the interface 2
func (a author) articles() {
    pendingarticles := a.tarticles - a.particles
    fmt.Printf("\nPending articles: %d", pendingarticles)
}

// Main value
func main() {

    // Assigning values
    // to the structure
    values := author{
        a_name:    "Mickey",
        branch:    "Computer science",
        college:   "XYZ",
        year:      2012,
        salary:    50000,
        particles: 209,
        tarticles: 309,
    }

    // Accessing the methods 
    // of the interface 1 and 2
    // Using FinalDetails interface
    var f FinalDetails = values
    f.details()
    f.articles()
}
```

**输出:**

```go
Author Name: Mickey
Branch: Computer science and passing year: 2012
College Name: XYZ
Salary: 50000
Published articles: 209
Pending articles: 100

```

**说明:**如上例所示，我们有三个接口。接口 1 和 2 是简单的接口，接口 3 是嵌入式接口，其中包含 1 和 2 接口方法签名。因此，如果接口 1 和接口 2 的方法发生任何变化，它将反映在接口 3 中。接口 3 可以访问接口 1 和 2 中的所有方法。

**例 3:**

```go
// Go program to illustrate the concept
// of the embedding interfaces
package main

import "fmt"

// Interface 1
type AuthorDetails interface {
    details()
}

// Interface 2
type AuthorArticles interface {
    articles()
    picked()
}

// Interface 3
// Interface 3 embedded with interface 
// 1's method and interface 2
// And also contain its own method
type FinalDetails interface {
    details()
    AuthorArticles
    cdeatils()
}

// Structure
type author struct {
    a_name    string
    branch    string
    college   string
    year      int
    salary    int
    particles int
    tarticles int
    cid       int
    post      string
    pick      int
}

// Implementing method 
// of the interface 1
func (a author) details() {

    fmt.Printf("Author Name: %s", a.a_name)
    fmt.Printf("\nBranch: %s and passing year: %d", a.branch, a.year)
    fmt.Printf("\nCollege Name: %s", a.college)
    fmt.Printf("\nSalary: %d", a.salary)
    fmt.Printf("\nPublished articles: %d", a.particles)
}

// Implementing methods 
// of the interface 2
func (a author) articles() {

    pendingarticles := a.tarticles - a.particles
    fmt.Printf("\nPending articles: %d", pendingarticles)
}

func (a author) picked() {

    fmt.Printf("\nTotal number of picked articles: %d", a.pick)
}

// Implementing the method
// of the embedded interface
func (a author) cdeatils() {

    fmt.Printf("\nAuthor Id: %d", a.cid)
    fmt.Printf("\nPost: %s", a.post)
}

// Main value
func main() {

    // Assigning values to the structure
    values := author{

        a_name:    "Mickey",
        branch:    "Computer science",
        college:   "XYZ",
        year:      2012,
        salary:    50000,
        particles: 209,
        tarticles: 309,
        cid:       3087,
        post:      "Technical content writer",
        pick:      58,
    }

    // Accessing the methods 
    // of the interface 1 and 2
    // Using FinalDetails interface
    var f FinalDetails = values
    f.details()
    f.articles()
    f.picked()
    f.cdeatils()
}
```

**输出:**

```go
Author Name: Mickey
Branch: Computer science and passing year: 2012
College Name: XYZ
Salary: 50000
Published articles: 209
Pending articles: 100
Total number of picked articles: 58
Author Id: 3087
Post: Technical content writer

```

**说明:**如上例所示，我们有三个接口。接口 1 和 2 是简单的接口，接口 3 是嵌入式接口，它保存接口 1 的方法签名、接口 2 和它自己的方法。因此，如果接口 1 的方法和接口 2 发生任何变化，它将反映在接口 3 中。接口 3 可以访问其中的所有方法，包括接口 1、2 和它自己的方法。