# 标量中的纯函数

> 原文:[https://www.geeksforgeeks.org/pure-function-in-scala/](https://www.geeksforgeeks.org/pure-function-in-scala/)

在任何编程语言中，都有两种类型的函数:

**1。纯功能**

**2。不纯功能**

这两者之间有一个基本的区别，那就是纯函数不会改变它传递的变量，而不纯函数会。例如，存在将输入增加 10 的函数。所以，有两种可能，第一种是它可以直接**返回 x + 10** ，所以 x 不变，而在另一种情况下，它可以用像 **x = x + 10** 这样的语句，然后返回 x，从而改变 x 的值。所以，第一个函数是**纯**，而另一个是**不纯**。

## 标量中的纯函数

如果一个函数总是为相同的参数值返回相同的结果，并且它没有像修改参数(或全局变量)或输出某些东西那样的副作用，那么它就被称为纯函数。
它们是那些除了作为输入给出的值之外不读取任何其他值并遵循其内部算法产生输出的函数。一个纯函数是**无副作用的**，也就是说，它不会隐式改变变量的值，因此最终不会改变输入的值。
这些 Scala String 方法也是纯函数:

*   伊西普西伊普西伊普西伊普西伊普西伊普西伊普西伊普西伊普西伊普西伊普西伊普西伊普西伊普西伊普西伊普西
*   长度
*   子链

可以做一个纯函数，如下面的程序代码所示:
**例 1:**

## 斯卡拉

```scala
// Pure function In Scala
object GFG
{
    // Driver code
    def main(args: Array[String])
    {
        def square(a:Int) = {
            var b:Int = a * a;
            println("Square of the number is " + b);
            println("Number is " + a);
        }
        square(4);
    }
}
```

**输出:**

```scala
Square of the number is 16
Number is 4
```

现在，我们知道这些函数不会隐式改变变量，所以我们以不同的方式添加两个不同函数的结果，如图所示:
**例 2:**

## 斯卡拉

```scala
// Scala Pure Function
object GFG
{
    // Driver code
    def main(args: Array[String])
    {
        // Function 1
        def add(a:Int, b:Int):Int = {
            var c:Int = a + b;
            return c;
        }

        // Function 2
        def multiply(a:Int, b:Int):Int = {
            var c:Int = a * b;
            return c;
        }

        // Calculating same value but changing
        // the position of the functions
        println("Output in case 1 :" +
                add(1, 2) * multiply(3, 4));
        println("Output in case 2 :" +
                multiply(4, 3) * add(2, 1));
    }
}
```

**输出:**

```scala
Output in case 1 :36
Output in case 2 :36
```

现在，由于这两种情况的输出是相同的，那么就证明了 scala 中纯函数的输入是不隐式改变的。
**以下是使用纯函数的合适方式:**

1.  它们不会在输入中引起任何隐含的变化。
2.  它们更容易测试。
3.  它们很容易调试。