# 在 Scala 中将 Java 字符串集转换为向量的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-strings-to-vector-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-strings-to-a-vector-in-scala/)

利用 Scala 中 java 的 *toVector* 方法，可以将一组 Java 字符串转换为 Scala 中的一个向量。在这里，您需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作，否则将会出现错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set
// to a Vector in Scala

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
        set.add("Geeks")
        set.add("for")
        set.add("Geeks")

        // Converting set to a Vector 
        val vec= set.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(Geeks, for)

```

因此，结果输出的顺序与上面列表中的顺序相同，重复的输出也被删除。
**例:2#**

```scala
// Scala program to convert Java set
// to a Vector in Scala

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
        set.add("My")
        set.add("name is")
        set.add("Nidhi")

        // Converting set to a Vector 
        val vec= set.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(Nidhi, My, name is)

```

这里，所述的字符串没有按正确的顺序排列，但是结果输出是按正确的顺序排列的。像这里一样，具有更多字数的字符串最后显示，更长的字符串首先显示。