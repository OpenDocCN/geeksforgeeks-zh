# 在 Scala 中将 Java 双精度集合转换为字符串的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-of-double-to-string-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-doubles-to-a-string-in-scala/)

利用 Scala 中 java 的 *toString* 方法，可以将一组 Java 双精度值转换为 Scala 中的字符串。在这里，您需要导入 Scala 的 *JavaConversions* 对象，以便进行转换。
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

        // Creating set of doubles in Java
        val set = new java.util.HashSet[Double]()

        // Adding doubles to the set
        set.add(2.23)
        set.add(3.10)
        set.add(4.2)

        // Converting set to a String
        val str = set.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[3.1, 2.23, 4.2]

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

        // Creating set of doubles in Java
        val set = new java.util.HashSet[Double]()

        // Adding doubles to the set
        set.add(3.22)
        set.add(4.22)
        set.add(6.22)

        // Converting set to a String
        val str = set.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[4.22, 6.22, 3.22]

```