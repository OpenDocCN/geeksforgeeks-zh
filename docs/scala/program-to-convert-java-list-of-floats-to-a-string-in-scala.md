# 在 Scala 中将 Java 浮点列表转换为字符串的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-float-to-string-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-floats-to-a-string-in-scala/)

利用 Scala 中 java 的 *toString* 方法，可以将一个 Java 的浮点列表转换成 Scala 中的字符串。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作。
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

        // Creating list of floats in Java
        val list = new java.util.ArrayList[Float]()

        // Adding floats to the list
        list.add(1.1f)
        list.add(5.1f)
        list.add(7.1f)

        // Converting list to a String
        val str = list.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[1.1, 5.1, 7.1]

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

        // Creating list of floats in Java
        val list = new java.util.ArrayList[Float]()

        // Adding characters to the list
        list.add(5.3f)
        list.add(7.9f)
        list.add(6.3f)

        // Converting list to a String
        val str = list.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[5.3, 7.9, 6.3]

```