# 斯卡拉|密封特质

> 原文:[https://www.geeksforgeeks.org/scala-sealed-trait/](https://www.geeksforgeeks.org/scala-sealed-trait/)

**密封**为我们的应用提供*详尽的检查*。彻底检查允许检查密封特征的所有成员必须在源文件的同一个文件中声明。这意味着编译器预先知道必须包含的特性的所有可能的已知成员。所以这给了我们防止代码错误的优势。

**语法:**

```scala
sealed trait X
class A extends X
class B extends X
class C extends X

```

穷举检查主要用于 scala 中的 type / [模式匹配](https://www.geeksforgeeks.org/scala-pattern-matching/)。假设我们有一个密封的特征 X 和扩展特征 X 的类。在匹配特征 X 的子类型时，我们必须确保包含所有已知的子类型是必须的。下面的方法会给我们一个警告。虽然我们会得到正确的输出，但这可能会导致我们的应用程序意外的运行时崩溃。

```scala
Warning: match may not be exhaustive

```

```scala
def obj(item: X) = item match {
   case A => //
   case B => //
}

```

正确的实施就像-

```scala
def obj(item: X) = item match{
   case A => //
   case B => //
   case C => //
   or 
   case _ => //for covering all the remaining cases
}

```

让我们来看看下面这个以文件保存为**语言的程序**

**示例:**

## 斯卡拉

```scala
// Scala Program that illustrates sealed trait
// language.scala
sealed trait Geeks
{
    val article="not done"
}

// Class extends trait
class Scala extends Geeks
{
    override val article = "scala article"
}

// Class extends trait
class Java extends Geeks
{
    override val article = "java article"
}

// Class extends trait
class Csharp extends Geeks
{
    override val article = "csharp article"
}

// Creating object
object GFG
{
    // Main method
    def main(args: Array[String])
    {
        val s = new Scala
        val j = new Java
        val c = new Csharp
        println(checkArticle(s))
        println(checkArticle(j))
        println(checkArticle(c))
    }

    // Defined function
    def checkArticle(Article: Geeks): String = Article match
    {
        case s: Scala  => s.article
        case j: Java   => j.article
        case c: Csharp => c.article
        //exclusion of <strong>line 45</strong> would lead to warning
    }
}
```

**输出:**

```scala
scala article
java article
csharp article

```

**some important points**

*   **一个性状的子类型是事先知道的-** 在模式匹配中不包括任何密封类 C 的子类型会给我们警告。这样的警告告诉您，您的代码可能会产生匹配错误异常，因为一些可能的模式没有被处理。该警告指出了运行时错误的潜在来源，因此它通常有助于您的程序正确运行。

*   **密封特征只能在子类型的同一个源文件中扩展-** 在上面的例子中，我们在另一个 scala 文件中有另一个类 **python** 。从**语言导入特性**极客**。Scala**我们会得到如下错误消息。

```scala
illegal inheritance from sealed trait bag

```

```scala
import geeks
class python extends geeks{
    val article="python article";
}

```

*   **密封类也多用于** [**枚举**](https://www.geeksforgeeks.org/enumeration-in-scala/)–防止非法继承，使用所有子类型，避免穷举匹配警告。
    **例:**

## 斯卡拉

```scala
// Scala Program that illustrates sealed trait
// By using Enumeration
sealed trait card extends Enumeration

// Class extends trait
case object CLUB extends card

// Class extends trait
case object HEART extends card

// Class extends trait
case object DIAMOND extends card

// Class extends trait
case object SPADE extends card

// Creating object
object obj1
{  
    // Main method
    def main(args: Array[String])
    {
        val card1 = HEART
        val card2 = CLUB
        val card3 = SPADE
        val card4 = DIAMOND
        println(checkcard(card1))
        println(checkcard(card2))
        println(checkcard(card3))
        println(checkcard(card4))
    }

    // Defined function
    def checkcard(x: card): String = x match
    {

        case HEART   =>"heart"
        case CLUB    =>"club"
        case SPADE   =>"spade"
        case DIAMOND =>"diamond"
    }
}
```

**输出:**

```scala
heart
club
spade
diamond

```