# 对比戈朗地图

> 原文:[https://www.geeksforgeeks.org/comparing-maps-in-golang/](https://www.geeksforgeeks.org/comparing-maps-in-golang/)

在 Go 语言中，[](https://www.geeksforgeeks.org/golang-maps/)**是一种强大、巧妙、通用的数据结构。Golang Maps 是无序的键值对的集合。它被广泛使用，因为它提供了快速的查找和值，可以在键的帮助下检索、更新或删除。
在 Go 语言中，您可以使用反射包提供的 **DeepEqual()** 功能来比较两张地图。如果两个映射都满足以下条件，则此函数返回 true:**

*   **两张地图都是零或非零。**
*   **两张地图长度相同。**
*   **两个映射是同一个映射对象，或者它们对应的键映射到深度相等的值。**

**否则，此函数返回 false。**

****语法:****

```go
reflect.DeepEqual(a, b) 
```

**这里 *a 和 b 是映射*，这个函数检查 a 和 b 是否深度相等，然后返回布尔型结果。**

****示例:****

## **去**

```go
// Go program to illustrate
// how to compare two maps
package main

import (
    "fmt"
    "reflect"
)

func main() {

    map_1 := map[int]string{

        200: "Anita",
        201: "Neha",
        203: "Suman",
        204: "Robin",
        205: "Rohit",
    }
    map_2 := map[int]string{

        200: "Anita",
        201: "Neha",
        203: "Suman",
        204: "Robin",
        205: "Rohit",
        206: "Sumit",
    }

    map_3 := map[int]string{

        200: "Anita",
        201: "Neha",
        203: "Suman",
        204: "Robin",
        205: "Rohit",
    }
    map_4 := map[string]int{

        "Anita": 200,
        "Neha":  201,
        "Suman": 203,
        "Robin": 204,
        "Rohit": 205,
    }

    // Comparing maps
    // Using DeepEqual() function
    res1 := reflect.DeepEqual(map_1, map_2)
    res2 := reflect.DeepEqual(map_1, map_3)
    res3 := reflect.DeepEqual(map_1, map_4)
    res4 := reflect.DeepEqual(map_2, map_3)
    res5 := reflect.DeepEqual(map_3, map_4)
    res6 := reflect.DeepEqual(map_4, map_4)
    res7 := reflect.DeepEqual(map_2, map_4)

    // Displaying result
    fmt.Println("Is Map 1 is equal to Map 2: ", res1)
    fmt.Println("Is Map 1 is equal to Map 3: ", res2)
    fmt.Println("Is Map 1 is equal to Map 4: ", res3)
    fmt.Println("Is Map 2 is equal to Map 3: ", res4)
    fmt.Println("Is Map 3 is equal to Map 4: ", res5)
    fmt.Println("Is Map 4 is equal to Map 4: ", res6)
    fmt.Println("Is Map 2 is equal to Map 4: ", res7)

}
```

****输出:****

```go
Is Map 1 is equal to Map 2:  false
Is Map 1 is equal to Map 3:  true
Is Map 1 is equal to Map 4:  false
Is Map 2 is equal to Map 3:  false
Is Map 3 is equal to Map 4:  false
Is Map 4 is equal to Map 4:  true
Is Map 2 is equal to Map 4:  false 
```