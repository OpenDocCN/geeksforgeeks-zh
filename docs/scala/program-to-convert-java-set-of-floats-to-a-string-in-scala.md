# 在 Scala 中将 Java 浮点集合转换为字符串的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-float-to-string-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-floats-to-a-string-in-scala/)

利用 Scala 中 java 的 *toString* 方法，可以将一组 Java 浮点转换为 Scala 中的字符串。在这里，您需要导入 Scala 的 *JavaConversions* 对象，以便进行转换。
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

        // Creating set of floats in Java
        val set = new java.util.HashSet[Float]()

        // Adding floats to the set
        set.add(3.2f)
        set.add(6.4f)
        set.add(9.6f)

        // Converting set to a String
        val str = set.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[3.2, 6.4, 9.6]

```

这里，对于集合的每个元素，十进制后的数字是不同的，因此，结果输出按十进制后的数字的升序排列。
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

        // Creating set of floats in Java
        val set = new java.util.HashSet[Float]()

        // Adding floats to the set
        set.add(2.1f)
        set.add(3.1f)
        set.add(1.1f)

        // Converting set to a String
        val str = set.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[2.1, 3.1, 1.1]

```

这里，对于列表中的所有元素，小数点后的数字都是相同的，因此，结果输出的顺序与上述相同。