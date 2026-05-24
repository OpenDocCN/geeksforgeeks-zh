# 响。Golang 中的 Link()函数示例

> 原文:[https://www . geesforgeks . org/ring-link-function-in-golang-with-examples/](https://www.geeksforgeeks.org/ring-link-function-in-golang-with-examples/)

**响。Golang 中的 Link()** 函数用于连接两个环 r 和环 s 环，next()函数将环 r 的最后一个节点连接到环 s 的第一个节点，这样 for r.next()就不能为空。否则，它将抛出一个错误。它像一个循环链表一样工作。

**语法:**

```go
func (r *Ring) Link(s *Ring) *Ring
```

它不返回任何东西。

**例 1:**

```go
// Golang program to illustrate
// the ring.Link() function
package main

import (
    "container/ring"
    "fmt"
)

// Main function
func main() {

    // Create two rings, a and b, of size 2
    a := ring.New(4)
    b := ring.New(4)

    // Get the length of the ring
    m := a.Len()
    n := b.Len()

    // Initialize a with 0s
    for j := 0; j < m; j++ {
        a.Value = 0
        a = a.Next()
    }

    // Initialize b with 1s
    for i := 0; i < n; i++ {
        b.Value = 1
        b = b.Next()
    }

    // Link ring a and ring b
    ab := a.Link(b)

    ab.Do(func(p interface{}) {
        fmt.Println(p.(int))
    })

}
```

**输出:**

```go
0
0
0
0
1
1
1
1

```

**例 2:**

```go
// Golang program to illustrate
// the ring.Link() function
package main

import (
    "container/ring"
    "fmt"
)

// Main function
func main() {

    // Create two rings, r and s, of size 2
    r := ring.New(2)
    s := ring.New(2)

    // Get the length of the ring
    lr := r.Len()
    ls := s.Len()

    // Initialize r with "GFG"
    for i := 0; i < lr; i++ {
        r.Value = "GFG"
        r = r.Next()
    }

    // Initialize s with "COURSE"
    for j := 0; j < ls; j++ {
        s.Value = "COURSE"
        s = s.Next()
    }

    // Link ring r and ring s
    rs := r.Link(s)

    // Iterate through the combined
    // ring and print its contents
    rs.Do(func(p interface{}) {
        fmt.Println(p.(string))
    })
}
```

**输出:**

```go
GFG
GFG
COURSE
COURSE

```