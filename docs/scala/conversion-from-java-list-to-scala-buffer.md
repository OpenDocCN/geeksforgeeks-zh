# 从 Java 列表到 Scala 缓冲区的转换

> 原文:[https://www . geesforgeks . org/conversion-from-Java-list-to-Scala-buffer/](https://www.geeksforgeeks.org/conversion-from-java-list-to-scala-buffer/)

一个 Java 列表可以通过导入 JavaConversions.asScalaBuffer 方法转换成一个 Scala Buffer。这里，我们需要调用**作为一个以 java 列表为参数的**方法。因此，这个方法返回一个 Scala 缓冲区。
现在，让我们来看一些例子。
**例:1#**

```scala
// Scala program of converting a Java list
// to a Scala Buffer

// Importing JavaConversions.asScalaBuffer
import scala.collection.JavaConversions.asScalaBuffer

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating Java List
        val jlist = java.util.Arrays.asList(11, 12, 13)

        // Converting from java list
        // to Scala Buffer
        val results= asScalaBuffer(jlist)

        // Displays results
        println(results)
    }
}
```

**Output:**

```scala
Buffer(11, 12, 13)

```

因此，会返回一个 Scala 缓冲区。
**例:2#**

```scala
// Scala program of converting a Java list
// to a Scala Buffer

// Importing JavaConversions.asScalaBuffer
import scala.collection.JavaConversions.asScalaBuffer

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating Java List
        val jlist = java.util.Arrays.asList(6, 2, 8, 1)

        // Converting from java list
        // to Scala Buffer
        val results= asScalaBuffer(jlist)

        // Displays results
        println(results)
    }
}
```

**Output:**

```scala
Buffer(6, 2, 8, 1)

```