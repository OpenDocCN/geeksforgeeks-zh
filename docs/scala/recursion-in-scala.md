# Scala 中的递归

> 原文:[https://www.geeksforgeeks.org/recursion-in-scala/](https://www.geeksforgeeks.org/recursion-in-scala/)

递归是一种将问题分解成更小的子问题并为每个问题调用自身的方法。也就是简单的表示 ***函数调用自身*** 。我们可以用递归代替循环。递归*避免与循环*相关的可变状态。递归在函数式编程中非常常见，它为描述许多算法提供了一种自然的方式。递归被认为在函数式编程中很重要。Scala 非常支持递归。

让我们用简单的阶乘例子来理解。
**例:**

```scala
// Scala program of factorial using recursion

// Creating object
object GFG
{
    // Function define
    def fact(n:Int): Int=
    {
        if(n == 1) 1
        else n * fact(n - 1)
    }

    // Main method
    def main(args:Array[String])
    {
        println(fact(3))
    }
}
```

**输出:**

```scala
6
```

上面的代码演示了阶乘函数的*递归*方法，其中条件 **n == 1** 导致递归中断。

让我们通过一个 gcd 的例子来更清楚地理解。
**例:**

```scala
// Scala program of GCD using recursion

// Creating object
object GFG
{
    // Function defined
    def gcd(x:Int, y:Int): Int=
    {
        if (y == 0) x
        else gcd(y, x % y)
    }

    // Main method
    def main(args:Array[String])
    {
        println(gcd(12, 18))
    }
}
```

**输出:**

```scala
6
```

递归的问题是，如果我们不小心，深度递归会炸掉堆栈。
我们用一个例子来理解一下:
**示例代码:**

```scala
// Scala program of sum all numbers
// using recursion

// Creating object
object GFG
{
    // Function defined
    def sum(num: Int): Int=
    {
        if (num == 1)
            1
        else
            sum(num - 1) + num
    }

    // Main method
    def main(args:Array[String])
    {
        println(sum(55))
    }
}
```

**输出:**

```scala
1540
```

求和方法将对所有数字求和。我们每次都减少*数*，并将其加到结果中。这里，每当我们调用 sum 时，它都会在堆栈上留下输入值 *num* ，并且每次都会耗尽内存。当我们尝试传递像 sum(555555)这样的大输入时，输出将是**。该输出意味着堆栈已被放大。**

上面的例子没有使用*尾部递归*，因此不是一个最佳的方法，尤其是如果起始值 n 非常大。

**Tail Recursion**

尾部递归函数被认为优于非尾部递归函数，因为尾部递归可以被编译器优化。如果递归调用是函数做的最后一件事，那么递归函数被称为**尾递归**。没有必要记录以前的状态。
让我们通过一个例子来理解它:

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

在上面的代码中，我们可以使用**@ tairec**注释来确认我们的算法是尾部递归的。

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

```scala
Could not optimize @tailrec annotated method factorial: it contains a recursive call not in tail position
```