# Scala 中的尾部递归

> 原文:[https://www.geeksforgeeks.org/tail-recursion-in-scala/](https://www.geeksforgeeks.org/tail-recursion-in-scala/)

[递归](https://www.geeksforgeeks.org/recursion-in-scala/)是将问题分解成更小的子问题，并为每个问题调用自己的方法。也就是说，它仅仅意味着函数调用自己。**尾部递归函数**比非尾部递归函数更好，因为尾部递归可以被编译器优化。如果递归调用是函数做的最后一件事，则递归函数被称为尾部递归。没有必要记录以前的状态。

对于尾部递归函数，程序中将使用一个包`**import scala.annotation.tailrec**`。

**语法:**

```scala
@tailrec
def FuntionName(Parameter1, Parameter2, ...): type = …
```

让我们通过例子来理解尾部递归。

**示例:**

```scala
// Scala program of GCD using recursion 
import scala.annotation.tailrec

// Creating object 
object GFG 
{ 
    // Function defined 
    def GCD(n: Int, m: Int): Int =
    {
        // tail recursion function defined 
        @tailrec def gcd(x:Int, y:Int): Int=
        { 
            if (y == 0) x 
            else gcd(y, x % y) 
        } 
        gcd(n, m)
    } 

    // Main method 
    def main(args:Array[String]) 
    { 
        println(GCD(12, 18)) 
    } 
} 
```

**输出:**

```scala
6
```

从上面的例子中我们可以看到`@tailrec`用于 gcd 函数，也就是尾部递归函数。通过使用尾部递归，不需要记录 gcd 函数的先前状态。

**示例:**

```scala
// Scala program of factorial using tail recursion 
import scala.annotation.tailrec 

// Creating object 
object GFG 
{ 
    // Function defined 
    def factorial(n: Int): Int =
    { 
        // Using tail recursion 
        @tailrec def factorialAcc(acc: Int, n: Int): Int =
        { 
            if (n <= 1) 
                acc 
            else 
                factorialAcc(n * acc, n - 1) 
        } 
        factorialAcc(1, n) 
    } 

    // Main method 
    def main(args:Array[String]) 
    { 
        println(factorial(5)) 
    } 
} 
```

**输出:**

```scala
120
```

在上面的代码中，我们可以使用`@tailrec`注释来确认我们的算法是尾部递归的。

如果我们使用这个注释，并且我们的算法不是尾部递归的，编译器会抱怨。例如，如果我们试图在上面的阶乘方法的例子中使用这个注释，我们将得到下面的编译时错误。

**示例:**

```scala
// Scala program of factorial with tail recursion 
import scala.annotation.tailrec 

// Creating object 
object GFG 
{ 
    // Function defined 
    @tailrec def factorial(n: Int): Int =
    { 
        if (n == 1) 
            1
        else 
            n * factorial(n - 1) 
    } 

    // Main method 
    def main(args:Array[String]) 
    { 
        println(factorial(5)) 
    } 
} 
```

**输出:**

> 无法优化@tailrec 注释方法阶乘:它包含不在尾部位置的递归调用。