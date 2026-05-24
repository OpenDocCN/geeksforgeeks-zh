# 在 Scala 中将 Java 字节列表转换为字符串的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-bytes-to-string-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-bytes-to-a-string-in-scala/)

利用 Scala 中 java 的 *toString* 方法，可以将 Java 字节列表转换为 Scala 中的字符串。在这里，您需要导入 Scala 的 *JavaConversions* 对象，以便进行转换。
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

        // Creating list of bytes in Java
        val list = new java.util.ArrayList[Byte]()

        // Adding bytes to the list
        list.add(123)
        list.add(13)
        list.add(-11)

        // Converting list to a String
        val str = list.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[123, 13, -11]

```

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

        // Creating list of bytes in Java
        val list = new java.util.ArrayList[Byte]()

        // Adding bytes to the list
        list.add(-123)
        list.add(-124)
        list.add(-125)

        // Converting list to a String
        val str = list.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[-123, -124, -125]

```