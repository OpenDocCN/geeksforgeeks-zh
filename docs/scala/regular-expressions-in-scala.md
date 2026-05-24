# Scala 中的正则表达式

> 原文:[https://www.geeksforgeeks.org/regular-expressions-in-scala/](https://www.geeksforgeeks.org/regular-expressions-in-scala/)

**正则表达式**解释了一种用于匹配一系列输入数据的通用模式，因此它在众多编程语言的模式匹配中很有帮助。在 Scala 中*正则表达式*通常被称为 Scala *正则表达式*。
*Regex* 是从包`**scala.util.matching.Regex**`导入的类，广泛应用于搜索和文本解析。为了将字符串重铸为*正则表达式*，我们需要对所述字符串使用 **r()** 方法。

**示例:**

```scala
// Scala program for Regular 
// Expressions

// Creating object
object GfG 
{

    // Main method
    def main(args: Array[String]) 
    {

        // Applying r() method
        val portal = "GeeksforGeeks".r
        val CS = "GeeksforGeeks is a CS portal."

        // Displays the first match
        println(portal findFirstIn CS)
    }
}
```

**Output:**

```scala
Some(GeeksforGeeks)

```

在这里，我们调用了所述字符串上的方法 `r()`来获得`Regex class`的实例，以便创建一个模式。上面的代码中使用了`**findFirstIn()**`方法来查找正则表达式的第一个匹配项。为了找到表达式中所有匹配的单词，使用`**findAllIn()**`方法。

**示例:**

```scala
// Scala program for Regular 
// Expressions
import scala.util.matching.Regex

// Creating object
object GfG 
{

    // Main method
    def main(args: Array[String]) 
    {

        // Applying Regex class
        val x = new Regex("Nidhi")
        val myself = "My name is Nidhi Singh."

        // replaces first match with the
        // String given below
        println(x replaceFirstIn(myself, "Rahul"))
    }
}
```

**Output:**

```scala
My name is Rahul Singh.

```

我们甚至可以用 Regex 的构造函数代替`r()`方法。这里，使用`**replaceFirstIn()**`方法替换所述字符串的第一个匹配，并且我们甚至可以使用`**replaceAllIn()**`方法替换所有匹配。

**示例:**

```scala
// Scala program for Regular 
// Expressions
import scala.util.matching.Regex

// Creating object
object GfG 
{

    // Main method
    def main(args: Array[String]) 
    {

        // Applying Regex class
        val Geeks = new Regex("(G|g)fG")
        val y = "GfG is a CS portal. I like gfG"

        // Displays all the matches separated
        // by a separator
        println((Geeks findAllIn y).mkString(", "))
    }
}
```

**Output:**

```scala
GfG, gfG

```

这里，我们使用了 **mkString** 方法来连接所有匹配项，由分隔符分隔，并且在上面的代码中使用了一个管道( **|** )来搜索给定字符串中的大写和小写。因此，这里返回所述字符串的大小写。

**Syntax for Scala Regular Expressions**

Java 继承了 Perl 的一些特性，Scala 从 Java 继承了 Scala regex 的语法。下面是元字符语法列表:

| 子表达式 | 比赛 |
| --- | --- |
| **^** | 它用于匹配线的起点。 |
| **$** | 它用于匹配线路的终点。 |
| **。** | 它用于匹配除换行符以外的任何一个字符。 |
| **[……]** | 它用于匹配括号内的任何一个字符。 |
| **【^…】** | 它用于匹配不在括号中的任何一个字符。 |
| **\\A** | 它用于匹配完整字符串的起点。 |
| **\\z** | 它用于匹配完整字符串的终止点。 |
| **\\Z** | 它用于匹配除新行之外的整个字符串的结尾(如果存在)。 |
| **re*** | 它被用来匹配前述表达式的零个或多个外观。 |
| **re+** | 它用于匹配一个或多个前述表达式。 |
| **re？** | 它用于匹配前面表达式的零个或一个外观。 |
| **re{ n}** | 它用于精确匹配前面表达式的 n 个外观。 |
| **re{ n，}** | 它用于匹配前述表达式的 n 个或更多外观。 |
| **re{ n，m}** | 它用于匹配前述表达式的至少 n 个和最多 m 个外观。 |
| **q&#124;r** | 它用于匹配 q 或 r。 |
| **(re)** | 它用于对正则表达式进行分组，并对匹配的文本进行重新着色。 |
| **(？:re)** | 它还对正则表达式进行分组，但不重新收集匹配的文本。 |
| **(？> re)** | 它用于在没有回溯的情况下匹配自力更生的模式。 |
| **\\w** | 它用于匹配单词的字符。 |
| **\\W** | 它用于匹配非单词的字符。 |
| **\\s** | 它用于匹配类似于[\t\n\r\f]的空格。 |
| **\\S** | 它用于匹配非空格。 |
| **\\d** | 它用于匹配数字，即[0-9]。 |
| **\\D** | 它用于匹配非数字。 |
| **\\G** | 它用于匹配最末端的匹配点。 |
| **\\n** | 用于回参考占用组号 *n* 。 |
| **\\b** | 当单词 frontiers 在括号外时，它用于匹配单词 frontiers，当单词 backspace 在括号内时，它用于匹配 back space。 |
| **\\B** | 它用于匹配非单词边界。 |
| **\\n，\t 等。** | 它用于匹配换行符、制表符等。 |
| **\\Q** | 它用于转义(引用)每个字符直到\\E |
| **\\E** | 它用于以\\Q 开头的结尾引用 |