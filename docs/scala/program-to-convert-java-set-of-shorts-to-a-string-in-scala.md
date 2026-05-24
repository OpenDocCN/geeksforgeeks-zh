# 在 Scala 中把 Java 短集转换成字符串的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-shot-to-string-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-shorts-to-a-string-in-scala/)

利用 Scala 中 java 的 *toString* 方法，可以将一组 Java 短裤转换成 Scala 中的字符串。在这里，您需要导入 Scala 的 *JavaConversions* 对象，以便进行转换。
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

        // Creating set of shorts in Java
        val set = new java.util.HashSet[Short]()

        // Adding shorts to the set
        set.add(1000)
        set.add(-1000)
        set.add(111)
        set.add(-111)

        // Converting set to a String
        val str = set.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[-1000, 1000, -111, 111]

```

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

        // Creating set of shorts in Java
        val set = new java.util.HashSet[Short]()

        // Adding shorts to the set
        set.add(-1000)
        set.add(1000)
        set.add(-111)

        // Converting set to a String
        val str = set.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[-1000, 1000, -111]

```