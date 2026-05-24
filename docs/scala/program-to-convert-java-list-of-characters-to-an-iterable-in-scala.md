# 将 Java 字符列表转换为 Scala 中的 Iterable 的程序

> 原文:[https://www . geeksforgeeks . org/program-to-convert-Java-characters-list-to-an-iteratable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-characters-to-an-iterable-in-scala/)

利用 Scala 中 java 的*到*方法，可以将 Java 字符列表转换成 Scala 中的 Iterable。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换，否则会出现错误。
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

        // Creating list of characters in Java
        val list = new java.util.ArrayList[Char]()

        // Adding characters to the list
        list.add('x')
        list.add('y')
        list.add('z')

        // Converting list to an Iterable
        val iterab= list.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Buffer(x, y, z)

```

因此，返回一个缓冲区，元素以所述列表的顺序出现，并且这里没有消除重复的元素。
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

        // Creating list of characters in Java
        val list = new java.util.ArrayList[Char]()

        // Adding characters to the list
        list.add('y')
        list.add('z')
        list.add('x')

        // Converting list to an Iterable 
        val iterab= list.toIterable

        // Displays output
        println(iterab)

    }
}
```

**Output:**

```scala
Buffer(y, z, x)

```

这里，所述列表的顺序不正确，因此结果缓冲区的顺序也不正确。