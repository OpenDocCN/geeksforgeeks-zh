# 在 Scala 中将 Java 短列表转换为字符串的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-short-to-string-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-shorts-to-a-string-in-scala/)

利用 Scala 中 java 的 *toString* 方法，可以将一个 Java 的 shorts 列表转换成 Scala 中的 String。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作。
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

        // Creating list of shorts in Java
        val list = new java.util.ArrayList[Short]()

        // Adding shorts to the list
        list.add(1000)
        list.add(111)
        list.add(100)

        // Converting list to a String
        val str = list.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[1000, 111, 100]

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

        // Creating list of shorts in Java
        val list = new java.util.ArrayList[Short]()

        // Adding shorts to the list
        list.add(-100)
        list.add(-111)
        list.add(1000)

        // Converting list to a String
        val str = list.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[-100, -111, 1000]

```