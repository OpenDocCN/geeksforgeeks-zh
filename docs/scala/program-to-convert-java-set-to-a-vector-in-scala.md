# 在 Scala 中将 Java 集合转换为向量的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-to-a-vector-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-to-a-vector-in-scala/)

利用 Scala 中 java 的 *toVector* 方法，可以将一个 Java 集合转换成 Scala 中的一个向量。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set 
// to a Vector in Scala

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

        // Converting set to a vector
        val vec = set.toVector

        // Displays output
        println(vec)

    }
}
```

**Output:**

```scala
Vector(9, 10, 11)

```

因此，返回一个整数向量。这里，首先创建一个集合，利用 *add* 方法向其中添加整数元素。之后，使用*到矢量*方法将所述集合转换为矢量。
**例:2#**

```scala
// Scala program to convert Java set 
// to a Vector in Scala

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
        set.add(8)
        set.add(7)
        set.add(9)

        // Converting set to a vector
        val vec = set.toVector

        // Displays output
        println(vec)

    }
}
```

**Output:**

```scala
Vector(7, 8, 9)

```

它与上面的例子相同，但是这里集合的元素没有以适当的顺序出现。但是返回的向量是正确的。