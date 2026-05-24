# 将 Java 字符串集转换为 Scala 中可遍历的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-strings-to-a-traversable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-strings-to-a-traversable-in-scala/)

通过利用 Scala 中 java 的 *toTraversable* 方法，可以将一组 Java 字符串转换为 Scala 中的可遍历集合。在这里，我们需要导入 Scala 的 JavaConversions 对象，以便进行转换。
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

        // Creating set of Strings in Java
        val set = new java.util.HashSet[String]()

        // Adding Strings to the set
        set.add("i")
        set.add("am")
        set.add("good")

        // Converting set to a Traversable 
        val tra = set.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Set(i, am, good)

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

        // Creating set of Strings in Java
        val set = new java.util.HashSet[String]()

        // Adding Strings to the set
        set.add("i")
        set.add("am a")
        set.add("girl")

        // Converting set to a Traversable 
        val tra= set.toTraversable

        // Displays traversable 
        println(tra)

    }
}
```

**Output:**

```scala
Set(am a, i, girl)

```

这里，首先显示字数较多的字符串，最后显示长度较长的字符串。