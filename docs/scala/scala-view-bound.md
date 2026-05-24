# Scala–视图绑定

> 原文:[https://www.geeksforgeeks.org/scala-view-bound/](https://www.geeksforgeeks.org/scala-view-bound/)

Scala 中的类型界限是对类型参数或类型变量的限制。通过使用这些类型界限，我们可以为变量设置限制。这些界限有助于将我们的代码放入现实世界的例子中。我们需要对现实生活中的每个因素施加一定的限制和界限，这就是 Scala 中类型界限的作用。

Scala 支持三种类型的类型界限:

1.  [上限](https://www.geeksforgeeks.org/scala-upper-bound/)
2.  [下限](https://www.geeksforgeeks.org/scala-lower-bound/)
3.  视图绑定

这里我们将讨论视图绑定。

**视图绑定**是 Scala 中使用的类型绑定之一。视图绑定基本上用于自动使用现有隐式转换的地方。在一些程序中，为了解决任何问题，隐式转换都是自动完成的。视图绑定用于利用这些隐式转换。

**语法:**

```scala
[T <% S]
```

这里，T 是类型参数，S 是类型。下面的例子说明了 Scala 中视图绑定的概念:

**例 1:**

```scala
// Scala program to demonstrate view bound 

// Declaration of view bound
class GFG[T <% Ordered[T]](val firstNumber: T, 
                           val secondNumber: T) 
{
    def greaterNumber = if (firstNumber > 
                            secondNumber)firstNumber 
        else secondNumber
}

// Object created
object ViewBoundExample 
{

    // Driver code
    def main(args: Array[String]) 
    {
        val result = new GFG(24, 25)

        println(result.greaterNumber)
    }
}
```

**输出:**

```scala
25
```

**例 2:**

```scala
// Scala program to demonstrate view bound 

// Declaration of view bound
class GFG[T <% Ordered[T]](val first_Str: T, 
                           val second_Str: T) 
{
    def smaller_Str = if (first_Str < 
                          second_Str)first_Str 
        else second_Str
}

// Object created
object ScalaViewBound 
{

    // Driver code
    def main(args: Array[String]) 
    {
        val result = new GFG("GeeksforGeeks", "Scala")

        println(result.smaller_Str)
    }
}
```

**输出:**

```scala
GeeksforGeeks
```