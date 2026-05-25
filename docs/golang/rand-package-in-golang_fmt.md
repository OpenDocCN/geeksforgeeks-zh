# 格朗兰特套餐

> 原文:[https://www.geeksforgeeks.org/rand-package-in-golang/](https://www.geeksforgeeks.org/rand-package-in-golang/)

Go 语言在 `math/rand` 包的帮助下，为生成指定类型的随机数提供了内置支持。这个包实现了伪随机数生成器。这些随机数是由一个源生成的，每次程序运行时，这个源都会生成一个确定性的值序列。而且如果你想将随机数用于安全敏感的工作，那么就使用 `crypto/rand` 包。

**注:**本包使用`[0，n]`等数学区间表示法。

| 功能 | 描述 |
| --- | --- |
| `ExpFloat64` | 该函数返回范围`(0，+math.MaxFloat64]`内的指数分布的 `float64`。 |
| `Float32` | 这个函数从缺省源返回一个伪随机数`[0.0，1.0]`作为 `float32`。 |
| `Float64` | 这个函数以 `float64` 的形式从默认源返回一个`[0.0，1.0]`中的伪随机数。 |
| `Int` | 此函数从默认源返回一个非负伪随机 `int`。 |
| `Int31` | 此函数从默认源返回一个非负伪随机 31 位整数 `int32`。 |
| `Int31n` | 该函数以 `int32` 形式从默认源返回`[0，n]`中的非负伪随机数。 |
| `Int63` | 此函数从默认源返回一个非负伪随机 63 位整数 `int64`。 |
| `Int63n` | 该函数以 `int64` 形式从默认源返回`[0，n]`中的非负伪随机数。 |
| `Intn` | 该函数以 `int` 形式从默认源返回`[0，n]`中的非负伪随机数。 |
| `NormFloat64` | 这个函数返回一个范围为`[-math.MaxFloat64，+math.MaxFloat64]`的正态分布的 `float64`。标准正态分布(平均值= 0，stddev = 1)。 |
| `Perm` | 这个函数从缺省源返回整数`[0，n]`的伪随机排列，作为 `n` 个整数的一部分。 |
| `Read` | 此函数从默认源生成 `len(p)` 随机字节，并将它们写入 `p`。 |
| `Seed` | 该函数提供种子值，将默认源初始化为确定性状态，如果没有调用 `Seed`，生成器的行为就像 `Seed(1)` 播种的一样。 |
| `Shuffle` | 该函数使用默认源对元素的顺序进行伪随机化。 |
| `Uint32` | 该函数从默认源返回一个 32 位的伪随机值 `uint32`。 |
| `Uint64` | 该函数从默认源返回一个 64 位伪随机值 `uint64`。 |

## 边缘型

| 方法 | 描述 |
| --- | --- |
| `New` | 这个函数返回一个新的 `Rand`，它使用来自 `src` 的随机值来生成其他随机值。 |
| `func (*Rand) ExpFloat64` | 此方法用于返回`(0，+math.MaxFloat64]`范围内的指数分布的 `float64`。 |
| `func (*Rand) Float32` | 这个方法以 `float32` 的形式返回`[0.0，1.0]`中的伪随机数。 |
| `func (*Rand) Float64` | 此方法以 `float64` 形式返回`[0.0，1.0]`中的伪随机数。 |
| `func (*Rand) Int` | 此方法返回一个非负伪随机 `int`。 |
| `func (*Rand) Int31` | 此方法返回一个非负伪随机 31 位整数作为 `int32`。 |
| `func (*Rand) Int31n` | 此方法以 `int32` 形式返回`[0，n]`中的非负伪随机数。 |
| `func (*Rand) Int63` | 此方法返回一个非负伪随机 63 位整数作为 `int64`。 |
| `func (*Rand) Int63n` | 此方法以 `int64` 形式返回`[0，n]`中的非负伪随机数。 |
| `func (*Rand) Intn` | 此方法以 `int` 形式返回`[0，n]`中的非负伪随机数。 |
| `func (*Rand) NormFloat64` | 此方法用于返回范围`[-math.MaxFloat64，+math.MaxFloat64]`中的正态分布 `float64`。标准正态分布(均值= 0，stddev = 1)。 |
| `func (*Rand) Perm` | 此方法返回整数`[0，n]`的伪随机排列，作为 `n` 个整数的一部分。 |
| `func (*Rand) Read` | 此方法生成 `len(p)` 随机字节，并将它们写入 `p`。 |
| `func (*Rand) Seed` | 该方法提供了种子值来将生成器初始化为确定性状态。 |
| `func (*Rand) Shuffle` | 这种方法伪随机化元素的顺序。 |
| `func (*Rand) Uint32` | 此方法返回一个 32 位伪随机值作为 `uint32`。 |
| `func (*Rand) Uint64` | 此方法返回一个 64 位伪随机值作为 `uint64`。 |

## 型源

| 方法 | 描述 |
| --- | --- |
| `func NewSource` | 此函数返回一个新的伪随机源，该源以给定的值植入。 |
| `type Source64` | It is a `Source` that can also generate uniformly-distributed pseudo-random `uint64` values in the range `[0, 1<<64)` directly. if a `rand` r's underlying source s implements `Source64`, then r.Uint64 returns the result of one call to s.Uint64 instead making two calls s.Int63. |

## Zipf型

| 方法 | 描述 |
| --- | --- |
| `func NewZipf` | 这个函数返回一个 `Zipf` 变量生成器。 |
| `func (*Zipf) Uint64` | 此方法返回从 `Zipf` 对象描述的 `Zipf` 分布中提取的值。 |

**例 1:**

```go
// Golang program to illustrate
// how to Get Intn Type Random
// Number
package main

import (
    "fmt"
    "math/rand"
)

// Main function
func main() {

    // Finding random numbers of int type
    // Using Intn() function
    res_1 := rand.Intn(7)
    res_2 := rand.Intn(8)
    res_3 := rand.Intn(2)

    // Displaying the result
    fmt.Println("Random Number 1: ", res_1)
    fmt.Println("Random Number 2: ", res_2)
    fmt.Println("Random Number 3: ", res_3)
}
```

**输出:**

```go
Random Number 1:  6
Random Number 2:  7
Random Number 3:  1
```

**例 2:**

```go
// Golang program to illustrate
// how to get a random number
package main

import (
    "fmt"
    "math/rand"
)

// Main function
func main() {

    // Finding random numbers of int type
    // Using Int31() function
    res_1 := rand.Int31()
    res_2 := rand.Int31()
    res_3 := rand.Int31()

    // Displaying the result
    fmt.Println("Random Number 1: ", res_1)
    fmt.Println("Random Number 2: ", res_2)
    fmt.Println("Random Number 3: ", res_3)
}
```

**输出:**

```go
Random Number 1:  1298498081
Random Number 2:  2019727887
Random Number 3:  1427131847
```