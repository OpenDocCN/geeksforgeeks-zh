# 将 Java 字符集转换为 Scala 中可遍历字符的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-字符集-scala 中可遍历/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-characters-to-a-traversable-in-scala/)

通过利用 Scala 中 java 的 *toTraversable* 方法，可以将一组 Java 字符转换为 Scala 中的可遍历集合。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set 
// to a Traversable in Scala

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
        set.add('x')
        set.add('y')
        set.add('z')

        // Converting set to a Traversable 
        val tra = set.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Set(x, y, z)

```

这里，所述输出与给定集合中所述的顺序相同。
**例:2#**

```scala
// Scala program to convert Java set 
// to a Traversable in Scala

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
        set.add('g')
        set.add('f')
        set.add('e')

        // Converting set to a Traversable 
        val tra = set.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Set(e, f, g)

```

这里，所述集合不是以适当的顺序给出的，但是结果输出是以适当的顺序给出的。