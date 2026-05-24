# 在 Scala 中将 Java 字符集转换成字符串的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-字符集-字符串-in-scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-characters-to-a-string-in-scala/)

利用 Scala 中 java 的 *toString* 方法，可以将一组 Java 字符集转换为 Scala 中的字符串。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set 
// to a String in Scala

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

        // Converting set to a String
        val str = set.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[a, b, c]

```

这里，重复的元素被消除，并且集合中的元素的结果顺序与上述相同。
**例:2#**

```scala
// Scala program to convert Java set 
// to a String in Scala

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
        set.add('d')
        set.add('b')
        set.add('c')

        // Converting set to a String
        val str = set.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[b, c, d]

```

这里，所述的集合不是正确的顺序，但是结果输出是正确的顺序。