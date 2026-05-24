# 环包在戈朗

> 原文:[https://www.geeksforgeeks.org/ring-package-in-golang/](https://www.geeksforgeeks.org/ring-package-in-golang/)

Go 语言提供了一个实现循环列表操作的环形包。要访问环包的功能，您需要借助 import 关键字在程序中导入环包。

| 方法 | 描述 |
| **新功能** | 这种方法用于创建 n 个元素的环。 |
| **功能(*环)做** | 此方法用于以正向顺序调用环的每个元素上的函数 f。 |
| **[func (*Ring) Len](https://www.geeksforgeeks.org/ring-len-function-in-golang-with-examples/)** | 此方法用于计算 r 环中的元素数量。 |
| **[功能(*环)链接](https://www.geeksforgeeks.org/ring-link-function-in-golang-with-examples/)** | 这种方法用来连接环 r 和环 s。 |
| **功能(*环)移动** | 此方法用于在环中向后移动 n % r.Len()元素(n < 0) or forward (n > = 0)，并返回该环元素。 |
| **功能(*响铃)下一步** | 此方法用于返回下一个环元素。 |
| **func (*Ring)预测** | 此方法用于返回前一个环元素。 |
| **功能(*环)解除链接** | 此方法用于从给定的环中移除 n % r.Len()元素，从 r.Next()开始。 |

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

    // Creating a new ring of size 5
    r_ring := ring.New(5) 

    // Print out its length 
    fmt.Println(r_ring.Len()) 

} 
```

**输出:**

```go
5
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

    // Create two rings, r1 and r2, of size 3
    r1 := ring.New(3) 
    r2 := ring.New(3) 

    // Get the length of the ring 
    lr := r1.Len() 
    ls := r2.Len() 

    // Initialize r1 with "GFG" 
    for i := 0; i < lr; i++ { 
        r1.Value = "GFG"
        r1 = r1.Next() 
    } 

    // Initialize r2 with "GOLang" 
    for j := 0; j < ls; j++ { 
        r2.Value = "GoLang"
        r2 = r2.Next() 
    } 

    // Link ring r1 and ring r2 
    rs := r1.Link(r2) 

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
GFG
GoLang
GoLang
GoLang

```