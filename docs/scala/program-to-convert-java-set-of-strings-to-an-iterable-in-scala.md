# 在 Scala 中将 Java 字符串集转换为可迭代的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-of-strings-to-iteratable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-strings-to-an-iterable-in-scala/)

通过利用 Scala 中 java 的*到*方法，可以将一组 Java 字符串转换为 Scala 中的 Iterable。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set
// to an Iterable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set of Strings in Java
        val set = new java.util.HashSet[String]()

        // Adding Strings to the set
        set.add("geeks")
        set.add("for")
        set.add("geeks")

        // Converting set to an Iterable
        val iterab= set.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Set(geeks, for)

```

这里，重复的字符串被消除，结果输出是正确的顺序，因为所述的集合也是正确的顺序。
**例:2#**

```scala
// Scala program to convert Java set
// to an Iterable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set of Strings in Java
        val set = new java.util.HashSet[String]()

        // Adding integers to the set
        set.add("i")
        set.add("am an")
        set.add("author")

        // Converting set to an Iterable
        val iterab= set.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Set(author, i, am an)

```

这里，所述集合不是以适当的顺序陈述的，但是结果输出是以适当的顺序陈述的。因为首先显示字母数较多的字符串，最后显示单词数较多的字符串。