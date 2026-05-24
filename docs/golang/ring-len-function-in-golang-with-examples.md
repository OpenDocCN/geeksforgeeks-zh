# 响。Golang 中 Len()函数示例

> 原文:[https://www . geesforgeks . org/ring-len-function-in-golang-with-examples/](https://www.geeksforgeeks.org/ring-len-function-in-golang-with-examples/)

**响。Golang 中的 Len()** 函数计算环(循环列表)r 中的组件(元素)数量，它根据组件(元素)的数量及时执行。

**语法:**

```go
func (r *Ring) Len() int
```

它返回整数。

**例 1:**

```go
// Golang program to illustrate
// the ring.Len() function
package main

import (
    "container/ring"
    "fmt"
)
// Main function
func main() {

    // Creating a new ring of size 3
    r := ring.New(3)

    // Print out its length
    fmt.Println(r.Len())

}
```

**输出:**

```go
3
```

**例 2:**

```go
// Golang program to illustrate
// the ring.Len() function
package main

import (
    "container/ring"
    "fmt"
)
// Main function
func main() {
    // Creating a new ring of size 10
    r := ring.New(10)

    // Print out its length
    fmt.Println(r.Len())

}
```

**输出:**

```go
10
```