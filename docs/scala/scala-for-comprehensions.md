# 理解的标量

> 原文:[https://www.geeksforgeeks.org/scala-for-comprehensions/](https://www.geeksforgeeks.org/scala-for-comprehensions/)

**理解**具有结构`*for (enumerators) yield e*`，其中枚举器指的是以分号分隔的枚举器列表。枚举器要么是引入新变量的生成器，要么是*过滤器*。理解为枚举器生成的每个绑定评估主体 *e* ，并返回这些值的序列。

这些定义引导我们理解生成器、过滤器和定义。用于理解的 Scala 将包含以下 3 个表达式:

*   发电机
*   过滤
*   定义

**语法:**

```scala
for {
    b 
 **<font size="3.8">发电机- </font>** 发电机有以下几种形式:

```
pattern 例如 **b 在这个表达式中，值 b 迭代包含在书中的所有元素。
下面是关于发电机的另外两件事- >** 

```scala

```

*   每个理解都是从一个生成器开始的。
*   为了便于理解，将会有多个生成器。

<font size="3.8">**定义-**</font>

为了便于理解，定义有以下语法:

```scala
pattern = expression
```

例如`n = b.name`变量 n 被绑定到值 b.name。该语句的结果类似于为了理解而在 a 之外编写这段代码。`val n = b.name`

<font size="3.8">**过滤器-**</font>

对于理解过滤器有以下形式:

```scala
if (expression)
```

表达式具有布尔类型。*过滤器*删除迭代中表达式返回假的所有元素，就像给定的代码一样。例如`**if (n startsWith "Ca")**`任何不以字符串 *Ca* 开始的值 *n* 将在迭代过程中被丢弃。

我们来讨论一些例子。

**实施例#1:** 与*一起产生*

```scala
// Scala program of for comprehensions

// Creating object 
object Geeks 
{ 

    // Main method 
    def main(args: Array[String]) 
    { 
        // Creating case class    
        case class Language(name: String, article: Int)

        val LanguageBase = List(Language("Scala", 26),
                                Language("Csharp", 32),
                                Language("Perl", 42),
                                Language("Java", 22))

        // Applying for comprehensions
        // Generator
        // Definition
        val MoreThanTwenty = for (language <- LanguageBase
        if (language.article >=20 && language.article < 30))// Filters

         // i.e. add this to a list
          yield language.name 

        // Print more than twenty 
        MoreThanTwenty.foreach(name => println(name))

    } 
} 
```

**输出:**

```scala
Scala
Java
```

在上面的例子中，与 *yield* 语句一起使用的 for 循环实际上创建了一个列表。因为我们说屈服`**language.name**`，是一个`List[String]`。**语言是我们的发电机，`if (language.article >=20 && language.article < 30)`可能是一个守卫，过滤掉那些看起来不在 20 到 30 之间的文章。

**例 2:** 没有*产量***

**我们可以在理解中省略产量。在这种情况下，理解将返回单元。这可能是有帮助的，以防我们想要执行副作用。这里有一个类似上面的程序，不使用 yield。**

```scala
// Scala program to print Hello, Geeks! 
// by using object-oriented approach 

// creating object 
object Geeks { 

// Main method 
def main(args: Array[String]) 
{ 

def check(a: Int) =
   for (i <- 0 until 4;
        j <- 0 until 4 if i * j >= a)
   println(s"($i, $j)")

check(4)
} 
} 
```** 

**输出:**

```scala
(2, 2)
(2, 3)
(3, 2)
(3, 3)
```

在上例中， *a = 4* 。在第一次迭代中， *i = 0* 和 *j = 0* 所以 *i * j* 不大于等于 **a** ，因此不产生任何结果。 *j* 增加 3 次，然后 *i* 增加到 1。

->->->