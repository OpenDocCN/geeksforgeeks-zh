# 在 Scala 中将 Java 列表转换成字符串的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-to-string-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-to-a-string-in-scala/)

利用 Scala 中 java 的 *toString* 方法，可以将一个 Java 列表转换成 Scala 中的字符串。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使这个转换工作，否则会出现错误。
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

        // Creating list in Java
        val list = new java.util.ArrayList[Int]()

        // Adding integers to the list
        list.add(5)
        list.add(6)
        list.add(7)

        // Converting list to a String 
        val str = list.toString

        // Displays String
        println(str)

    }
}
```

**Output:**

```scala
[5, 6, 7]

```

因此，返回一个字符串。这里，首先创建一个列表，使用 *add* 方法将 int 元素添加到列表中。之后，使用*到字符串*方法将所述列表转换为字符串。
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

        // Creating list in Java
        val list = new java.util.ArrayList[Int]()

        // Adding integers to the list
        list.add(5)
        list.add(4)
        list.add(6)

        // Converting list to a String 
        val str = list.toString

        // Displays String
        println(str)

    }
}
```

**Output:**

```scala
[5, 4, 6]

```

它与上面的例子相同，但是这里没有保持列表的正确顺序，所以获得的输出也没有按照正确的顺序。