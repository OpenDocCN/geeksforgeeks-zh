# 在 Scala 中将 Java 字符串列表转换为字符串的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-string-to-string-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-strings-to-a-string-in-scala/)

利用 Scala 中 java 的 *toString* 方法，可以将 Java 字符串列表转换为 Scala 中的字符串。在这里，您需要导入 Scala 的 *JavaConversions* 对象，以便进行转换。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list
// to a String in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list of strings in Java
        val list = new java.util.ArrayList[String]()

        // Adding strings to the list
        list.add("geeks")
        list.add("for")
        list.add("geeks")

        // Converting list to a String
        val str = list.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[geeks, for, geeks]

```

这里，重复的元素没有被消除，列表中的元素的结果顺序与上述相同。
**例:2#**

```scala
// Scala program to convert Java list
// to a String in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list of strings in Java
        val list = new java.util.ArrayList[String]()

        // Adding strings to the list
        list.add("I")
        list.add("am a")
        list.add("writer")

        // Converting list to a String
        val str = list.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[I, am a, writer]

```

这里，所述列表没有按正确的顺序排列，因此，结果输出也没有按正确的顺序排列。