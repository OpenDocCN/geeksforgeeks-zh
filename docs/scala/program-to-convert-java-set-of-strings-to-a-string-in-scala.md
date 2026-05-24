# 在 Scala 中将 Java 字符串集转换为字符串的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-string-to-string-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-strings-to-a-string-in-scala/)

利用 Scala 中 java 的 *toString* 方法，可以将一组 Java 字符串转换为 Scala 中的字符串。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作。
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

        // Creating set of Strings in Java
        val set = new java.util.HashSet[String]()

        // Adding Strings to the set
        set.add("geeks")
        set.add("for")
        set.add("geeks")

        // Converting set to a String
        val str = set.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[geeks, for]

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

        // Creating set of Strings in Java
        val set = new java.util.HashSet[String]()

        // Adding Strings to the set
        set.add("I")
        set.add("am an")
        set.add("author")

        // Converting set to a String
        val str = set.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[author, I, am an]

```

这里，在结果输出中，首先显示更长的字符串，最后显示具有更多单词的字符串。