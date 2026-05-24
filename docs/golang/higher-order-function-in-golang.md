# 戈朗高阶函数

> 原文:[https://www . geesforgeks . org/高阶函数 in-golang/](https://www.geeksforgeeks.org/higher-order-function-in-golang/)

在 Go 语言中，如果函数满足以下条件之一，则称为高阶函数:
**1。将函数作为参数传递给另一个函数:**
如果一个函数作为参数传递给另一个函数，那么这种类型的函数称为高阶函数。这个作为参数的传递函数在 Go 语言中也被称为**回调函数或一级函数**。
如下例所示，这里 *Sphere()函数*以一个函数为自变量，返回 *vol float64* 为自变量。在 Main 函数中，我们创建了一个匿名函数，其签名与 Sphere 函数的参数相匹配，因此我们只需调用 Sphere()函数，并将结果作为参数传递给它。
**例:**

## c sharp . c sharp . c sharp . c sharp

```go
// Golang program to illustrate how to pass
// a function as an argument to another
// function
package main

import (
    "fmt"
    "math"
)

// Volume function takes
// a function as a argument
func Sphere(vol func(radius float64) float64) {

    fmt.Println("Volume of Sphere is:", vol(3))
}

// Main Function
func main() {

    volume_of_sphere := func(radius float64) float64 {
        result := 4 / 3 * math.Pi * radius * radius * radius
        return result
    }

    // Passing function as an
    // argument in Volume function
    Sphere(volume_of_sphere)
}
```

**输出:**

```go
Volume of Sphere is: 84.82300164692441
```

**2。从另一个函数返回函数:**
如果一个函数返回另一个函数，那么这种类型的函数被称为高阶函数。它也被称为一级函数。如下例所示，这里 *Sphere()* 函数返回一个匿名函数，该函数接受一个 float64 参数并返回一个 float64 参数。现在在 Main 函数中，sVol 存储 *Sphere()* 函数返回的函数，所以我们调用 *sVol* 并在其中传递一个参数。
**例:**

## c sharp . c sharp . c sharp . c sharp

```go
// Golang program to illustrate how to pass
// a function returns another function
package main

import (
    "fmt"
    "math"
)

// Here, Volume function returns
// an anonymous function
func Sphere() func(radius float64) float64 {

    result := func(radius float64) float64 {
        volume := 4 / 3 * math.Pi * radius * radius * radius
        return volume
    }

    return result

}

// Main Function
func main() {

    sVol := Sphere()
    fmt.Println("Volume of Sphere is:", sVol(5))
}
```

**输出:**

```go
Volume of Sphere is: 392.69908169872417
```