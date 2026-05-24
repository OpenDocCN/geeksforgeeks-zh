# Scala |闭包

> 原文:[https://www.geeksforgeeks.org/scala-closures/](https://www.geeksforgeeks.org/scala-closures/)

**Scala 闭包**是使用一个或多个自由变量的函数，该函数的返回值依赖于这些变量。自由变量是在闭包函数之外定义的，不包含在这个函数的参数中。所以闭包函数和正规函数的区别在于自由变量。一个**自由变量**是任何一种没有在函数中定义并且没有作为函数参数传递的变量。自由变量没有绑定到具有有效值的函数。该函数不包含任何自由变量的值。
**举例:**
如果我们定义一个函数如下所示:

```scala
def example(a:double) = a*p / 100
```

现在在运行上面的代码时，我们会得到一个错误，开始没有找到 p。所以现在我们给函数外的 **p** 一个值。

```scala
// defined the value of p as 10
val p = 10

// define this closure.
def example(a:double) = a*p / 100
```

现在上面的函数可以运行了，因为自由变量有一个值。现在，如果我们按如下方式运行函数:

```scala
Calling the function: example(10000)
Input: p = 10
Output: double = 1000.0

```

现在，如果自由变量的值改变了，闭包函数的值如何改变呢？
所以基本上闭包函数的作用是，取自由变量的最近状态，并相应地改变闭包函数的值。

```scala
Input: p = 10
Output: double = 1000.0

Input: p = 20
Output: double = 2000.0

```

根据自由变量的类型，闭包函数可以进一步分为*纯*和*不纯*函数。如果我们给自由变量一个类型**变量**，那么该变量在整个代码中随时都会改变值，因此可能导致闭包函数的值改变。因此这个闭包是一个不纯的函数。另一方面，如果我们声明类型为 **val** 的自由变量，那么变量的值保持不变，从而使闭包函数成为纯函数。

**示例:**

```scala
// Addition of two numbers with 
// Scala closure

// Creating object
object GFG
{
    // Main method
    def main(args: Array[String])
    {
        println( "Final_Sum(1) value = " + sum(1))
        println( "Final_Sum(2) value = " + sum(2))
        println( "Final_Sum(3) value = " + sum(3))
    }

    var a = 4

    // define closure function
    val sum = (b:Int) => b + a
}
```

**Output:**

```scala
Final_Sum(1) value = 5
Final_Sum(2) value = 6
Final_Sum(3) value = 7

```

这里，在上述程序函数中**和**是一个闭包函数。var a = 4 是不纯闭包。a 的值相同，b 的值不同。
T3】例:

```scala
// Scala closure program to print a string

// Creating object
object GFG
{
    // Main method
    def main(args: Array[String])
    {

        var employee = 50

        // define closure function
        val gfg = (name: String) => println(s"Company name is $name"+
                       s" and total no. of employees are $employee")

        gfg("geeksforgeeks")
    }
}
```

**Output:**

```scala
Company name is geeksforgeeks and total no. of employees are 50.

```

这里，在上面的例子中 **gfg** 是一个闭包。var employee 是可变变量，可以更改。