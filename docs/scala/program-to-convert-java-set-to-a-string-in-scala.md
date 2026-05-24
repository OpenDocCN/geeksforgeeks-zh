# 在 Scala 中将 Java Set 转换为字符串的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-to-string-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-to-a-string-in-scala/)

利用 Scala 中 java 的 *toString* 方法，可以将一个 Java 集合转换成 Scala 中的字符串。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作。
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

        // Creating set in Java
        val set = new java.util.HashSet[Int]()

        // Adding integers to the set
        set.add(9)
        set.add(10)
        set.add(11)

        // Converting set to a String
        val str = set.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[9, 10, 11]

```

因此，将返回的字符串。这里，首先创建一个集合，利用 *add* 方法向其中添加整数元素。之后利用*转字符串*方法将所述集合转换为字符串。
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

        // Creating set in Java
        val set = new java.util.HashSet[Int]()

        // Adding integers to the set
        set.add(3)
        set.add(1)
        set.add(2)

        // Converting set to a String
        val str = set.toString

        // Displays output
        println(str)

    }
}
```

**Output:**

```scala
[1, 2, 3]

```

它与上面的例子相同，但是这里集合的元素没有以适当的顺序出现。但是返回的字符串的顺序是正确的。