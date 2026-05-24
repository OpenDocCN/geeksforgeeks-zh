# 将 Java 字符串列表转换为 Scala 中可迭代列表的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-to-iteratable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-strings-to-an-iterable-in-scala/)

通过在 Scala 中使用 java 的*到*方法，可以将 Java 字符串列表转换为 Scala 中的 Iterable。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list 
// to an Iterable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list of Strings in Java
        val list = new java.util.ArrayList[String]()

        // Adding Strings to the list
        list.add("geeks")
        list.add("for")
        list.add("geeks")

        // Converting list to an Iterable
        val iterab= list.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Buffer(geeks, for, geeks)

```

因此，返回一个缓冲区，元素以所述列表的顺序出现，并且这里不消除重复的元素。
**例:2#**

```scala
// Scala program to convert Java list 
// to an Iterable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list of Strings in Java
        val list = new java.util.ArrayList[String]()

        // Adding Strings to the list
        list.add("I")
        list.add("am an")
        list.add("author")

        // Converting list to an Iterable 
        val iterab= list.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Buffer(I, am an, author)

```

这里，所陈述的列表没有按正确的顺序排列，因此结果输出也没有按正确的顺序排列。也就是说，字数较多的字符串不会显示在最后，它们会以缓冲区的形式按照列表中的说明返回。