# 将 Java 字符集转换为 Scala 中的 Iterable 的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-字符集-scala 中可迭代/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-characters-to-an-iterable-in-scala/)

利用 Scala 中 java 的*到*方法，可以将 Java 字符集转换为 Scala 中的 Iterable。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating set of characters in Java
        val set = new java.util.HashSet[Char]()

        // Adding characters to the set
        set.add('a')
        set.add('b')
        set.add('c')

        // Converting set to an Iterable
        val iterab= set.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Set(a, b, c)

```

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

        // Creating set of characters in Java
        val set = new java.util.HashSet[Char]()

        // Adding characters to the set
        set.add('y')
        set.add('z')
        set.add('x')

        // Converting set to an Iterable
        val iterab= set.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Set(x, y, z)

```

这里，所述集合不是以适当的顺序陈述的，但是结果输出是以适当的顺序陈述的。