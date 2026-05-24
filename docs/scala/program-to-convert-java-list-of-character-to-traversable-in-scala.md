# 在 Scala 中将 Java 字符列表转换为可遍历的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-of-character-to-traversable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-character-to-traversable-in-scala/)

利用 Scala 中 java 的 *toTraversable* 方法，可以将一个 Java 字符列表转换成 Scala 中的 Traversable 集合。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list 
// to a Traversable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list of character in Java
        val list = new java.util.ArrayList[Char]()

        // Adding characters to the list
        list.add('l')
        list.add('m')
        list.add('n')

        // Converting list to a Traversable 
        val tra = list.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Buffer(l, m, n)

```

这里，所述输出与给定列表中所述的顺序相同。
**例:2#**

```scala
// Scala program to convert Java list
// to a Traversable in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list of character in Java
        val list = new java.util.ArrayList[Char]()

        // Adding characters to the list
        list.add('b')
        list.add('c')
        list.add('a')

        // Converting list to a Traversable 
        val tra = list.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Buffer(b, c, a)

```

这里，所有陈述的字符没有按正确的顺序陈述，因此，结果输出也没有按正确的顺序。