# 在 Scala 中将 Java 字符集转换成向量的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-字符集-标量向量/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-characters-to-a-vector-in-scala/)

利用 Scala 中 java 的 *toVector* 方法，可以将一组 Java 字符集转换为 Scala 中的一个 Vector。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使这个转换工作，否则会发生错误。
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

        // Creating set of characters in Java
        val set = new java.util.HashSet[Char]()

        // Adding characters to the set
        set.add('a')
        set.add('b')
        set.add('c')

        // Converting set to a Vector 
        val vec= set.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(a, b, c)

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

        // Creating set of characters in Java
        val set = new java.util.HashSet[Char]()

        // Adding characters to the set
        set.add('c')
        set.add('a')
        set.add('b')

        // Converting set to a Vector 
        val vec = set.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(a, b, c)

```

这里，所述字符不是以适当的顺序陈述的，但是结果输出是以适当的顺序陈述的。