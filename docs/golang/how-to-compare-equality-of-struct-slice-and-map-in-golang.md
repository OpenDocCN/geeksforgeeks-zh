# 如何比较 Golang 中结构、切片和贴图的相等性？

> 原文:[https://www . geeksforgeeks . org/如何比较 golang 中的结构切片和映射等式/](https://www.geeksforgeeks.org/how-to-compare-equality-of-struct-slice-and-map-in-golang/)

在格朗，**反映。DeepEqual** 函数用于比较 Golang 中结构、切片和贴图的相等性。它用于检查两个元素是否“深度相等”。深度意味着我们在递归地比较对象的内容。两种截然不同的价值观永远不会完全相同。如果下列情况之一为真，则两个完全相同的类型完全相等

**1。当以下所有条件都成立时，** [切片](https://www.geeksforgeeks.org/slices-in-golang/)值完全相等:

*   他们都是零或者都不是零。
*   它们的长度相同。
*   要么它们具有相同的初始条目(即，&x[0] == &y[0])，要么它们对应的元素(最大长度)完全相等。

**2。** [结构](https://www.geeksforgeeks.org/structures-in-golang/)值只有在它们对应的字段(即导出和未导出的字段)深度相等时才深度相等。

**3。** [地图](https://www.geeksforgeeks.org/golang-maps/)值在下列各项为真时完全相等:

*   他们都是零或非零
*   它们的长度是一样的
*   它们对应的键具有完全相等的值

**注意:**我们需要导入反射包才能使用 DeepEqual。

**语法:**

```go
func DeepEqual(x, y interface{}) bool
```

**示例:**

```go
// Golang program to compare equality
// of struct, slice, and map
package main

import (
    "fmt"
    "reflect"
)

type structeq struct {
    X int
    Y string
    Z []int
}

func main() {
    s1 := structeq{X: 50,
        Y: "GeeksforGeeks",
        Z: []int{1, 2, 3},
    }
    s2 := structeq{X: 50,
        Y: "GeeksforGeeks",
        Z: []int{1, 2, 3},
    }

    // comparing struct
    if reflect.DeepEqual(s1, s2) {
        fmt.Println("Struct is equal")
    } else {
        fmt.Println("Struct is not equal")
    }

    slice1 := []int{1, 2, 3}
    slice2 := []int{1, 2, 3, 4}

    // comparing slice
    if reflect.DeepEqual(slice1, slice2) {
        fmt.Println("Slice is equal")
    } else {
        fmt.Println("Slice is not equal")
    }

    map1 := map[string]int{
        "x": 10,
        "y": 20,
        "z": 30,
    }
    map2 := map[string]int{
        "x": 10,
        "y": 20,
        "z": 30,
    }

    // comparing map
    if reflect.DeepEqual(map1, map2) {
        fmt.Println("Map is equal")
    } else {
        fmt.Println("Map is not equal")
    }
}
```

**输出:**

```go
Struct is equal
Slice is not equal
Map is equal

```

但是， **cmp。Equal** 是比较结构的较好工具。要使用这个，我们需要导入“github.com/google/go-cmp/cmp”包。

**示例:**

```go
package main

import (
    "fmt"
    "github.com/google/go-cmp/cmp"
)

type structeq struct {
    X int
    Y string
    Z []int
}

func main() {
    s1 := structeq{X: 50,
        Y: "GeeksforGeeks",
        Z: []int{1, 2, 3},
    }
    s2 := structeq{X: 50,
        Y: "GeeksforGeeks",
        Z: []int{1, 2, 3},
    }
    // comparing struct
    if cmp.Equal(s1, s2) {
        fmt.Println("Struct is equal")
    } else {
        fmt.Println("Struct is not equal")
    }
}
```

**输出:**

```go
Struct is equal

```