# 计算戈朗串中重复单词的数量

> 原文:[https://www . geesforgeks . org/counting-重复单词数-golang-string/](https://www.geeksforgeeks.org/counting-number-of-repeating-words-in-a-golang-string/)

给定一个字符串，任务是计算在 Golang 中该特定字符串中重复的单词数。

**例:**

```go
Input: s = "She is mother of my mother."
Output: She = 1     
         is = 1
         mother = 2
         of = 1
         my = 1

```

要计算重复单词的数量，首先将字符串作为输入，然后是**字符串。Fields()函数**用于拆分字符串。定义了一个函数“重复”来计算重复的单词数。

下面是 Golang 中计算给定字符串中重复单词数量的程序。

```go
// Golang program to count the number of
// repeating words in given Golang String
package main

import (
    "fmt"
    "strings"
)

func repetition(st string) map[string]int {

    // using strings.Field Function
    input := strings.Fields(st)
    wc := make(map[string]int)
    for _, word := range input {
        _, matched := wc[word]
        if matched {
            wc[word] += 1
        } else {
            wc[word] = 1
        }
    }
    return wc
}

// Main function
func main() {
    input := "betty bought the butter , the butter was bitter , " +
        "betty bought more butter to make the bitter butter better "
    for index, element := range repetition(input) {
        fmt.Println(index, "=", element)
    }
}
```

**输出:**

```go
the = 3
, = 2
bitter = 2
to = 1
make = 1
better = 1
betty = 2
bought = 2
butter = 4
was = 1
more = 1

```

**说明:**在上面的程序中，我们首先将一个字符串作为输入，然后使用字符串分割该字符串。Fields()函数。如果出现了相同的单词，计数将增加一个，否则将返回值 1，这意味着该单词在字符串中只出现一次。