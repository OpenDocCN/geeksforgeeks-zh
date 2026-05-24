# 戈朗不同类型的递归

> 原文:[https://www . geesforgeks . org/golang 中不同类型的递归/](https://www.geeksforgeeks.org/different-types-of-recursion-in-golang/)

[递归](https://www.geeksforgeeks.org/recursion/)是一个函数通过直接或间接方式调用自身的概念。对递归函数的每次调用都是一个较小的版本，因此它会在某个点收敛。每个递归函数都有一个**基本情况**或基本条件，它是递归中的最终可执行语句，并停止进一步的调用。

如下例所示，递归有不同的类型:

### 1.直接递归

一种递归类型，其中函数直接调用自己，没有另一个函数的帮助，被称为直接递归。下面的例子解释了直接递归的概念:

**示例:**

```go
// Golang program to illustrate the
// concept of direct recursion
package main

import (
    "fmt"
)

// recursive function for 
// calculating a factorial 
// of a positive integer
func factorial_calc(number int) int {

    // this is the base condition
    // if number is 0 or 1 the
    // function will return 1
    if number == 0 || number == 1 {
        return 1
    }

    // if negative argument is 
    // given, it prints error
    // message and returns -1
    if number < 0 {
        fmt.Println("Invalid number")
        return -1
    }

    // recursive call to itself
    // with argument decremented 
    // by 1 integer so that it
    // eventually reaches the base case
    return number*factorial_calc(number - 1)
}

// the main function
func main() {

    // passing 0 as a parameter
    answer1 := factorial_calc(0)
    fmt.Println(answer1, "\n")

    // passing a positive integer
    answer2 := factorial_calc(5)
    fmt.Println(answer2, "\n")

    // passing a negative integer
    // prints an error message
    // with a return value of -1
    answer3 := factorial_calc(-1)
    fmt.Println(answer3, "\n")

    // passing a positive integer
    answer4 := factorial_calc(10)
    fmt.Println(answer4, "\n")
}
```

**输出:**

```go
1 

120 

Invalid number
-1 

3628800

```

### 2.间接递归

函数调用另一个函数，而这个函数又调用调用函数的递归类型称为间接递归。这种类型的递归需要另一个函数的帮助。该函数确实调用了自己，但是是间接的，即通过另一个函数。以下示例解释了间接递归的概念:

**示例:**

```go
// Golang program to illustrate the
// concept of indirect recursion
package main

import (
    "fmt"
)

// recursive function for 
// printing all numbers 
// upto the number n
func print_one(n int) {

    // if the number is positive
    // print the number and call 
    // the second function
    if n >= 0 {
        fmt.Println("In first function:", n)
        // call to the second function
        // which calls this first
        // function indirectly
        print_two(n - 1)
    }
}

func print_two(n int) {

    // if the number is positive
    // print the number and call 
    // the second function
    if n >= 0 {
        fmt.Println("In second function:", n)
        // call to the first function
        print_one(n - 1)
    }
}

// main function
func main() {

    // passing a positive 
    // parameter which prints all 
    // numbers from 1 - 10
    print_one(10)

    // this will not print
    // anything as it does not
    // follow the base case
    print_one(-1)
}
```

**输出:**

```go
In first function: 10
In second function: 9
In first function: 8
In second function: 7
In first function: 6
In second function: 5
In first function: 4
In second function: 3
In first function: 2
In second function: 1
In first function: 0

```

**注:**只有 2 个函数的间接递归称为相互递归。可以有 2 个以上的函数来促进间接递归。

### 3.尾部递归

尾部调用是子程序调用，是函数的最后一次或最后一次调用。当尾部调用执行对同一函数的调用时，该函数被称为尾部递归函数。这里，递归调用是函数执行的最后一件事。

**示例:**

```go
// Golang program to illustrate the
// concept of tail recursion
package main

import (
    "fmt"
)

// tail recursive function
// to print all numbers 
// from n to 1
func print_num(n int) {

    // if number is still 
    // positive, print it
    // and call the function
    // with decremented value
    if n > 0 {
        fmt.Println(n)

        // last statement in 
        // the recursive function
        // tail recursive call
        print_num(n-1)
    }
}

// main function
func main() {

    // passing a positive 
    // number, prints 5 to 1
    print_num(5)
}
```

**输出:**

```go
5
4
3
2
1

```

### 4.头部递归

在头部递归中，递归调用是函数中的第一条语句。在调用之前没有其他语句或操作。该函数不必在调用时处理任何东西，所有操作都在返回时完成。

**示例:**

```go
// Golang program to illustrate the
// concept of head recursion
package main

import (
    "fmt"
)

// head recursive function
// to print all numbers 
// from 1 to n
func print_num(n int) {

    // if number is still 
    // less than n, call 
    // the function
    // with decremented value
    if n > 0 {

        // first statement in 
        // the function
        print_num(n-1)

        // printing is done at
        // returning time
        fmt.Println(n)
    }
}

// main function
func main() {

    // passing a positive 
    // number, prints 5 to 1
    print_num(5)
}
```

**输出:**

```go
1
2
3
4
5

```

**注:**头部递归的输出与尾部递归的输出正好相反。这是因为尾部递归首先打印数字，然后调用自己，而在头部递归中，函数不断调用自己，直到到达基本大小写，然后在返回过程中开始打印。

### 5.无限递归

所有的递归函数都是确定的或有限的递归函数，也就是说，它们在达到基本条件时停止。无限递归是一种递归类型，它一直持续到无穷大，并且永远不会收敛到基本情况。这通常会导致系统崩溃或内存溢出。

**示例:**

```go
// Golang program to illustrate the
// concept of infinite recursion
package main

import (
    "fmt"
)

// infinite recursion function
func print_hello() {

    // printing infinite times
    fmt.Println("GeeksforGeeks")
    print_hello()
}

// main function
func main() {

    // call to infinite 
    // recursive function
    print_hello()
}
```

**输出:**

```go
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
..... infinite times

```

### 6.匿名函数递归

在 Golang 中，有一个没有名字的函数概念。这种函数称为匿名函数。递归也可以使用 Golang 中的匿名函数来执行，如下所示:

**示例:**

```go
// Golang program to illustrate 
// the concept of anonymous 
// function recursion
package main

import (
    "fmt"
)

// main function
func main() {

    // declaring anonymous function
    // that takes an integer value
        var anon_func func(int)

    // defining an anonymous
    // function that prints
    // numbers from n to 1
        anon_func = func(number int) {

        // base case
            if number == 0 {
                    return 
            } else {
            fmt.Println(number)

            // calling anonymous 
            // function recursively
                    anon_func(number-1)
            }
        }

    // call to anonymous 
    // recursive function
        anon_func(5)
}
```

**输出:**

```go
5
4
3
2
1

```