# 在 Scala 中将 Java 字符列表转换成字符串的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-characters-to-string-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-characters-to-a-string-in-scala/)

利用 Scala 中 java 的 *toString* 方法，可以将 Java 字符列表转换为 Scala 中的字符串。在这里，您需要导入 Scala 的 *JavaConversions* 对象，以便进行转换。
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

        // Creating list of character in Java
        val list = new java.util.ArrayList[Char]()

        // Adding characters to the list
        list.add('l')
        list.add('m')
        list.add('n')

        // Converting list to a String
        val str = list.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[l, m, n]

```

这里，重复的元素被消除，列表中的元素的结果顺序与上述相同。
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

        // Creating list of character in Java
        val list = new java.util.ArrayList[Char]()

        // Adding characters to the list
        list.add('d')
        list.add('b')
        list.add('c')

        // Converting list to a String
        val str = list.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[d, b, c]

```

这里，所述列表没有按正确的顺序排列，因此，结果输出也没有按正确的顺序排列。